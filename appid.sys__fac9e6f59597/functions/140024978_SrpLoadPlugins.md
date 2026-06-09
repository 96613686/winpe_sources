# SrpLoadPlugins

- ea: `0x140024978`
- end: `0x140024c47`
- name: `SrpLoadPlugins`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140023c04`

## callees

- `0x140001970`
- `0x140001e4c`
- `0x140006f40`
- `0x140024978`
- `0x140024c50`
- `0x140024d70`
- `0x1400295e8`
- `0x140029714`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140024a88`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140024a88`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140024b13`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140024b77`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140024b13`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140024b77`
- `ntoskrnl!ZwClose` at `0x140024aa1`
- `ntoskrnl!ZwClose` at `0x140024aa1`

## string_xrefs

- `0x140024b03`: `\SystemRoot\System32\AppLocker\{........-....-....-....-............}.Policy`
- `0x140024b70`: `\SystemRoot\System32\AppLocker\{........-....-....-....-............}.Policy`
- `0x140024be3`: `\SystemRoot\System32\AppLocker\{%08x-%04hx-%04hx-%02x%02x-%02x%02x%02x%02x%02x%02x}.Policy`

## pseudocode

```c
__int64 __fastcall SrpLoadPlugins(__int64 a1)
{
  int v2; // eax
  NTSTATUS Policy; // ebx
  _OWORD *v4; // rax
  __int64 *v5; // rdi
  int Plugins; // eax
  __int64 v7; // rcx
  __int64 v9; // rdi
  __int64 v10; // rax
  void *v11; // rax
  unsigned int *v12; // r12
  __int64 v13; // rax
  __int64 v14; // r13
  struct _UNICODE_STRING *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-98h]
  __int64 v17; // [rsp+28h] [rbp-90h]
  __int64 v18; // [rsp+30h] [rbp-88h]
  __int64 v19; // [rsp+38h] [rbp-80h]
  __int64 v20; // [rsp+40h] [rbp-78h]
  __int64 v21; // [rsp+48h] [rbp-70h]
  __int64 v22; // [rsp+50h] [rbp-68h]
  __int64 v23; // [rsp+58h] [rbp-60h]
  __int64 v24; // [rsp+60h] [rbp-58h]
  __int64 v25; // [rsp+68h] [rbp-50h]
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-48h] BYREF
  int v27; // [rsp+C0h] [rbp+8h]
  HANDLE Handle; // [rsp+C8h] [rbp+10h] BYREF

  Handle = 0;
  *(_DWORD *)(a1 + 16) = 0;
  UnicodeString = 0;
  v2 = SrpOpenFile(a1, &Handle);
  Policy = v2;
  if ( v2 >= 0 )
  {
    v5 = (__int64 *)(a1 + 24);
    Plugins = AiGetPlugins(Handle, (_QWORD *)(a1 + 24));
    Policy = Plugins;
    if ( Plugins >= 0 )
    {
      v9 = *v5;
      v10 = *(unsigned int *)(v9 + 28);
      if ( !(_DWORD)v10 )
        goto LABEL_14;
      v11 = (void *)AiAlloc(48 * v10);
      *(_QWORD *)(a1 + 32) = v11;
      if ( v11 )
      {
        memset(v11, 0, 48LL * *(unsigned int *)(v9 + 28));
        *(_DWORD *)(a1 + 40) = *(_DWORD *)(v9 + 28);
        if ( RtlCreateUnicodeString(
               &UnicodeString,
               L"\\SystemRoot\\System32\\AppLocker\\{........-....-....-....-............}.Policy") )
        {
          v12 = (unsigned int *)(v9 + *(unsigned int *)(v9 + 24));
          v13 = 0;
          while ( 1 )
          {
            v27 = v13;
            if ( (unsigned int)v13 >= *(_DWORD *)(a1 + 40) )
              goto LABEL_14;
            v14 = 48 * v13;
            v15 = (struct _UNICODE_STRING *)(48 * v13 + *(_QWORD *)(a1 + 32) + 16LL);
            if ( UnicodeString.Buffer )
            {
              *v15 = UnicodeString;
              UnicodeString = 0;
            }
            else if ( !RtlCreateUnicodeString(
                         v15,
                         L"\\SystemRoot\\System32\\AppLocker\\{........-....-....-....-............}.Policy") )
            {
              break;
            }
            LODWORD(v25) = *((unsigned __int8 *)v12 + 15);
            LODWORD(v24) = *((unsigned __int8 *)v12 + 14);
            LODWORD(v23) = *((unsigned __int8 *)v12 + 13);
            LODWORD(v22) = *((unsigned __int8 *)v12 + 12);
            LODWORD(v21) = *((unsigned __int8 *)v12 + 11);
            LODWORD(v20) = *((unsigned __int8 *)v12 + 10);
            LODWORD(v19) = *((unsigned __int8 *)v12 + 9);
            LODWORD(v18) = *((unsigned __int8 *)v12 + 8);
            LODWORD(v17) = *((unsigned __int16 *)v12 + 3);
            LODWORD(v16) = *((unsigned __int16 *)v12 + 2);
            Policy = RtlStringCchPrintfW(
                       *(NTSTRSAFE_PWSTR *)(*(_QWORD *)(a1 + 32) + v14 + 24),
                       (unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + v14 + 18) >> 1,
                       L"\\SystemRoot\\System32\\AppLocker\\{%08x-%04hx-%04hx-%02x%02x-%02x%02x%02x%02x%02x%02x}.Policy",
                       *v12,
                       v16,
                       v17,
                       v18,
                       v19,
                       v20,
                       v21,
                       v22,
                       v23,
                       v24,
                       v25);
            if ( Policy < 0 )
              goto LABEL_14;
            Policy = SrpLoadPolicy(v14 + *(_QWORD *)(a1 + 32));
            if ( Policy < 0 )
              goto LABEL_14;
            v13 = (unsigned int)(v27 + 1);
            v12 += 4;
          }
        }
      }
    }
    else
    {
      *(_DWORD *)(a1 + 16) = Plugins;
      if ( Plugins == -1073741811 )
        AiRegWriteDwordValue(v7, (struct _UNICODE_STRING *)L"tv", (struct _UNICODE_STRING *)&qword_1400093A0, 1);
      v4 = (_OWORD *)AiAlloc(0x20u);
      *v5 = (__int64)v4;
      if ( v4 )
        goto LABEL_5;
    }
LABEL_13:
    Policy = -1073741801;
    goto LABEL_14;
  }
  if ( v2 == -1073741772 )
  {
    v4 = (_OWORD *)AiAlloc(0x20u);
    *(_QWORD *)(a1 + 24) = v4;
    if ( v4 )
    {
      Policy = 0;
LABEL_5:
      *v4 = 0;
      v4[1] = 0;
      goto LABEL_14;
    }
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_ZD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids,
      a1,
      v2);
LABEL_14:
  RtlFreeUnicodeString(&UnicodeString);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x140024978  mov     rax, rsp
0x14002497b  mov     [rax+18h], rbx
0x14002497f  push    rbp
0x140024980  push    rsi
0x140024981  push    rdi
0x140024982  push    r12
0x140024984  push    r13
0x140024986  push    r14
0x140024988  push    r15
0x14002498a  sub     rsp, 80h
0x140024991  xorps   xmm0, xmm0
0x140024994  mov     qword ptr [rax+10h], 0
0x14002499c  lea     rdx, [rax+10h]
0x1400249a0  mov     dword ptr [rcx+10h], 0
0x1400249a7  movups  xmmword ptr [rax-48h], xmm0
0x1400249ab  mov     r15, rcx
0x1400249ae  call    SrpOpenFile
0x1400249b3  mov     ebx, eax
0x1400249b5  test    eax, eax
0x1400249b7  jns     short loc_140024A26
0x1400249b9  cmp     eax, 0C0000034h
0x1400249be  jnz     short loc_1400249E8
0x1400249c0  mov     ecx, 20h ; ' '
0x1400249c5  call    AiAlloc
0x1400249ca  mov     [r15+18h], rax
0x1400249ce  test    rax, rax
0x1400249d1  jz      loc_140024A7E
0x1400249d7  xor     ebx, ebx
0x1400249d9  xorps   xmm0, xmm0
0x1400249dc  movups  xmmword ptr [rax], xmm0
0x1400249df  movups  xmmword ptr [rax+10h], xmm0
0x1400249e3  jmp     loc_140024A83
0x1400249e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249ef  lea     rax, WPP_GLOBAL_Control
0x1400249f6  cmp     rcx, rax
0x1400249f9  jz      loc_140024A83
0x1400249ff  test    dword ptr [rcx+2Ch], 200h
0x140024a06  jz      short loc_140024A83
0x140024a08  mov     rcx, [rcx+18h]
0x140024a0c  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140024a13  mov     edx, 0Bh
0x140024a18  mov     dword ptr [rsp+0B8h+var_98], ebx
0x140024a1c  mov     r9, r15
0x140024a1f  call    WPP_SF_ZD
0x140024a24  jmp     short loc_140024A83
0x140024a26  mov     rcx, [rsp+0B8h+Handle]; Handle
0x140024a2e  lea     rdi, [r15+18h]
0x140024a32  mov     rdx, rdi
0x140024a35  call    AiGetPlugins
0x140024a3a  mov     ebx, eax
0x140024a3c  test    eax, eax
0x140024a3e  jns     loc_140024ACB
0x140024a44  mov     [r15+10h], eax
0x140024a48  cmp     eax, 0C000000Dh
0x140024a4d  jnz     short loc_140024A68
0x140024a4f  mov     r9d, 1
0x140024a55  lea     r8, qword_1400093A0
0x140024a5c  lea     rdx, aTv; "tv"
0x140024a63  call    AiRegWriteDwordValue
0x140024a68  mov     ecx, 20h ; ' '
0x140024a6d  call    AiAlloc
0x140024a72  mov     [rdi], rax
0x140024a75  test    rax, rax
0x140024a78  jnz     loc_1400249D9
0x140024a7e  mov     ebx, 0C0000017h
0x140024a83  lea     rcx, [rsp+0B8h+UnicodeString]; UnicodeString
0x140024a88  call    cs:__imp_RtlFreeUnicodeString
0x140024a8f  nop     dword ptr [rax+rax+00h]
0x140024a94  mov     rcx, [rsp+0B8h+Handle]; Handle
0x140024a9c  test    rcx, rcx
0x140024a9f  jz      short loc_140024AAD
0x140024aa1  call    cs:__imp_ZwClose
0x140024aa8  nop     dword ptr [rax+rax+00h]
0x140024aad  mov     eax, ebx
0x140024aaf  mov     rbx, [rsp+0B8h+arg_10]
0x140024ab7  add     rsp, 80h
0x140024abe  pop     r15
0x140024ac0  pop     r14
0x140024ac2  pop     r13
0x140024ac4  pop     r12
0x140024ac6  pop     rdi
0x140024ac7  pop     rsi
0x140024ac8  pop     rbp
0x140024ac9  retn
0x140024acb  mov     rdi, [rdi]
0x140024ace  mov     eax, [rdi+1Ch]
0x140024ad1  test    eax, eax
0x140024ad3  jz      short loc_140024A83
0x140024ad5  lea     rcx, [rax+rax*2]
0x140024ad9  shl     rcx, 4
0x140024add  call    AiAlloc
0x140024ae2  mov     [r15+20h], rax
0x140024ae6  mov     rcx, rax; void *
0x140024ae9  test    rax, rax
0x140024aec  jz      short loc_140024A7E
0x140024aee  mov     eax, [rdi+1Ch]
0x140024af1  xor     edx, edx; Val
0x140024af3  lea     r8, [rax+rax*2]
0x140024af7  shl     r8, 4; Size
0x140024afb  call    memset
0x140024b00  mov     eax, [rdi+1Ch]
0x140024b03  lea     rdx, aSystemrootSyst_1; "\\SystemRoot\\System32\\AppLocker\\{..."...
0x140024b0a  lea     rcx, [rsp+0B8h+UnicodeString]; DestinationString
0x140024b0f  mov     [r15+28h], eax
0x140024b13  call    cs:__imp_RtlCreateUnicodeString
0x140024b1a  nop     dword ptr [rax+rax+00h]
0x140024b1f  test    al, al
0x140024b21  jz      loc_140024A7E
0x140024b27  mov     r12d, [rdi+18h]
0x140024b2b  add     r12, rdi
0x140024b2e  xor     eax, eax
0x140024b30  mov     [rsp+0B8h+arg_0], eax
0x140024b37  cmp     eax, [r15+28h]
0x140024b3b  jnb     loc_140024A83
0x140024b41  mov     rcx, [r15+20h]
0x140024b45  lea     r13, [rax+rax*2]
0x140024b49  shl     r13, 4
0x140024b4d  add     rcx, 10h
0x140024b51  add     rcx, r13; DestinationString
0x140024b54  cmp     [rsp+0B8h+UnicodeString.Buffer], 0
0x140024b5a  jz      short loc_140024B70
0x140024b5c  movaps  xmm0, xmmword ptr [rsp+0B8h+UnicodeString.Length]
0x140024b61  xorps   xmm1, xmm1
0x140024b64  movdqu  xmmword ptr [rcx], xmm0
0x140024b68  movdqa  xmmword ptr [rsp+0B8h+UnicodeString.Length], xmm1
0x140024b6e  jmp     short loc_140024B8B
0x140024b70  lea     rdx, aSystemrootSyst_1; "\\SystemRoot\\System32\\AppLocker\\{..."...
0x140024b77  call    cs:__imp_RtlCreateUnicodeString
0x140024b7e  nop     dword ptr [rax+rax+00h]
0x140024b83  test    al, al
0x140024b85  jz      loc_140024A7E
0x140024b8b  movzx   ecx, byte ptr [r12+0Eh]
0x140024b91  movzx   r8d, byte ptr [r12+0Dh]
0x140024b97  mov     r14, [r15+20h]
0x140024b9b  movzx   r9d, byte ptr [r12+0Ch]
0x140024ba1  movzx   eax, byte ptr [r12+0Fh]
0x140024ba7  movzx   r10d, byte ptr [r12+0Bh]
0x140024bad  movzx   r11d, byte ptr [r12+0Ah]
0x140024bb3  movzx   ebx, byte ptr [r12+9]
0x140024bb9  movzx   edi, byte ptr [r12+8]
0x140024bbf  movzx   esi, word ptr [r12+6]
0x140024bc5  movzx   edx, word ptr [r14+r13+12h]
0x140024bcb  movzx   ebp, word ptr [r12+4]
0x140024bd1  mov     dword ptr [rsp+0B8h+var_50], eax
0x140024bd5  mov     dword ptr [rsp+0B8h+var_58], ecx
0x140024bd9  mov     rcx, [r14+r13+18h]; pszDest
0x140024bde  mov     dword ptr [rsp+0B8h+var_60], r8d
0x140024be3  lea     r8, aSystemrootSyst_0; "\\SystemRoot\\System32\\AppLocker\\{%08"...
0x140024bea  mov     dword ptr [rsp+0B8h+var_68], r9d
0x140024bef  mov     r9d, [r12]
0x140024bf3  mov     dword ptr [rsp+0B8h+var_70], r10d
0x140024bf8  mov     dword ptr [rsp+0B8h+var_78], r11d
0x140024bfd  mov     dword ptr [rsp+0B8h+var_80], ebx
0x140024c01  mov     dword ptr [rsp+0B8h+var_88], edi
0x140024c05  mov     dword ptr [rsp+0B8h+var_90], esi
0x140024c09  shr     rdx, 1; cchDest
0x140024c0c  mov     dword ptr [rsp+0B8h+var_98], ebp
0x140024c10  call    RtlStringCchPrintfW
0x140024c15  mov     ebx, eax
0x140024c17  test    eax, eax
0x140024c19  js      loc_140024A83
0x140024c1f  mov     rcx, [r15+20h]
0x140024c23  add     rcx, r13
0x140024c26  call    SrpLoadPolicy
0x140024c2b  mov     ebx, eax
0x140024c2d  test    eax, eax
0x140024c2f  js      loc_140024A83
0x140024c35  mov     eax, [rsp+0B8h+arg_0]
0x140024c3c  inc     eax
0x140024c3e  add     r12, 10h
0x140024c42  jmp     loc_140024B30
```
