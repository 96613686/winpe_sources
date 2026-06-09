# AiGetUninstallStringEa

- ea: `0x140020a70`
- end: `0x140020c1f`
- name: `AiGetUninstallStringEa`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140020db4`
- `0x140022d58`

## callees

- `0x140006a20`
- `0x140020a70`
- `0x1400328b0`
- `0x140032a50`
- `0x140036ee0`

## import_xrefs

- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x140020b2a`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x140020b2a`
- `ntoskrnl!_stricmp` at `0x140020b4b`
- `ntoskrnl!_stricmp` at `0x140020b4b`

## string_xrefs

- `0x140020abb`: `$Kernel.Smartlocker.UninstallStrings`
- `0x140020b44`: `$Kernel.Smartlocker.UninstallStrings`

## pseudocode

```c
__int64 __fastcall AiGetUninstallStringEa(__int64 a1, __int64 *a2, _DWORD *a3, __int64 *a4)
{
  __int64 v8; // rdi
  char v9; // bp
  unsigned int v10; // esi
  int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // eax
  int v15; // [rsp+38h] [rbp-B0h]
  unsigned int v16; // [rsp+50h] [rbp-98h] BYREF
  __int64 v17; // [rsp+58h] [rbp-90h]
  char v18[48]; // [rsp+68h] [rbp-80h] BYREF

  v16 = 0;
  v8 = 0;
  v9 = 0;
  v17 = 0;
  v10 = 612;
  AiAddEaToQueryBuffer((void *)"$Kernel.Smartlocker.UninstallStrings");
  *a4 = 0;
  while ( 1 )
  {
    AiFree(v8);
    v8 = AiAlloc(v10);
    if ( !v8 )
      return 3221225495LL;
    LOBYTE(v15) = 0;
    v11 = FsRtlQueryKernelEaFile(a1, v8, v10, 0, v18, 44, 0, v15, &v16);
    if ( v11 < 0 )
      break;
    if ( !_stricmp((const char *)(v8 + 8), "$Kernel.Smartlocker.UninstallStrings") )
    {
      if ( *(_WORD *)(v8 + 6) < 0x2Cu || v16 < 0x88 )
      {
        *a2 = 0;
        v11 = -1073741275;
        *a3 = 0;
        goto LABEL_12;
      }
      v12 = v8 + *(unsigned __int8 *)(v8 + 5) + 9LL;
      v13 = *(_DWORD *)(v12 + 36) + 90;
      if ( v13 < 0x5C )
      {
        v11 = -1073741675;
        break;
      }
      if ( v10 >= v13 )
      {
        *a2 = v12;
        *a3 = *(unsigned __int16 *)(v8 + 6);
        *a4 = v8;
        v8 = 0;
        v11 = 0;
        break;
      }
      if ( v9 )
      {
        v11 = -1073741789;
        break;
      }
      v9 = 1;
      v10 = *(_DWORD *)(v12 + 36) + 90;
    }
    else
    {
LABEL_12:
      if ( !v9 )
        break;
    }
  }
  AiFree(v8);
  if ( v11 >= 0 && (!*a2 || !*a3) )
    return (unsigned int)-1073741275;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140020a70  push    rbx
0x140020a72  push    rbp
0x140020a73  push    rsi
0x140020a74  push    rdi
0x140020a75  push    r12
0x140020a77  push    r13
0x140020a79  push    r14
0x140020a7b  push    r15
0x140020a7d  sub     rsp, 0A8h
0x140020a84  mov     rax, cs:__security_cookie
0x140020a8b  xor     rax, rsp
0x140020a8e  mov     [rsp+0E8h+var_50], rax
0x140020a96  mov     r12, r9
0x140020a99  mov     [rsp+0E8h+var_98], 0
0x140020aa1  mov     r14, r8
0x140020aa4  lea     r9, [rsp+0E8h+var_88]
0x140020aa9  mov     r15, rdx
0x140020aac  lea     r8, [rsp+0E8h+var_80]
0x140020ab1  mov     r13, rcx
0x140020ab4  lea     rdx, [rsp+0E8h+var_90]
0x140020ab9  xor     edi, edi
0x140020abb  lea     rcx, aKernelSmartloc; "$Kernel.Smartlocker.UninstallStrings"
0x140020ac2  xor     bpl, bpl
0x140020ac5  mov     [rsp+0E8h+var_90], rdi
0x140020aca  mov     esi, 264h
0x140020acf  call    AiAddEaToQueryBuffer
0x140020ad4  mov     [r12], rdi
0x140020ad8  mov     ebx, 2Ch ; ','
0x140020add  mov     rcx, rdi
0x140020ae0  call    AiFree
0x140020ae5  mov     ecx, esi
0x140020ae7  call    AiAlloc
0x140020aec  mov     rdi, rax
0x140020aef  test    rax, rax
0x140020af2  jz      loc_140020BF5
0x140020af8  lea     rax, [rsp+0E8h+var_98]
0x140020afd  xor     r9d, r9d
0x140020b00  mov     [rsp+0E8h+var_A8], rax
0x140020b05  mov     r8d, esi
0x140020b08  mov     [rsp+0E8h+var_B0], 0
0x140020b0d  lea     rax, [rsp+0E8h+var_80]
0x140020b12  mov     [rsp+0E8h+var_B8], 0
0x140020b1b  mov     rdx, rdi
0x140020b1e  mov     [rsp+0E8h+var_C0], ebx
0x140020b22  mov     rcx, r13
0x140020b25  mov     [rsp+0E8h+var_C8], rax
0x140020b2a  call    cs:__imp_FsRtlQueryKernelEaFile
0x140020b31  nop     dword ptr [rax+rax+00h]
0x140020b36  mov     ebx, eax
0x140020b38  test    eax, eax
0x140020b3a  js      loc_140020BD4
0x140020b40  lea     rcx, [rdi+8]; Str1
0x140020b44  lea     rdx, aKernelSmartloc; "$Kernel.Smartlocker.UninstallStrings"
0x140020b4b  call    cs:__imp__stricmp
0x140020b52  nop     dword ptr [rax+rax+00h]
0x140020b57  test    eax, eax
0x140020b59  jnz     short loc_140020BAA
0x140020b5b  lea     ebx, [rax+2Ch]
0x140020b5e  cmp     [rdi+6], bx
0x140020b62  jb      short loc_140020B97
0x140020b64  cmp     [rsp+0E8h+var_98], 88h
0x140020b6c  jb      short loc_140020B97
0x140020b6e  movzx   ecx, byte ptr [rdi+5]
0x140020b72  add     rcx, 9
0x140020b76  add     rcx, rdi
0x140020b79  mov     eax, [rcx+24h]
0x140020b7c  add     eax, 5Ah ; 'Z'
0x140020b7f  cmp     eax, 5Ch ; '\'
0x140020b82  jb      short loc_140020BCF
0x140020b84  cmp     esi, eax
0x140020b86  jnb     short loc_140020BBB
0x140020b88  test    bpl, bpl
0x140020b8b  jnz     short loc_140020BB4
0x140020b8d  mov     bpl, 1
0x140020b90  mov     esi, eax
0x140020b92  jmp     loc_140020ADD
0x140020b97  mov     qword ptr [r15], 0
0x140020b9e  mov     ebx, 0C0000225h
0x140020ba3  mov     dword ptr [r14], 0
0x140020baa  test    bpl, bpl
0x140020bad  jz      short loc_140020BD4
0x140020baf  jmp     loc_140020AD8
0x140020bb4  mov     ebx, 0C0000023h
0x140020bb9  jmp     short loc_140020BD4
0x140020bbb  mov     [r15], rcx
0x140020bbe  movzx   eax, word ptr [rdi+6]
0x140020bc2  mov     [r14], eax
0x140020bc5  mov     [r12], rdi
0x140020bc9  xor     edi, edi
0x140020bcb  xor     ebx, ebx
0x140020bcd  jmp     short loc_140020BD4
0x140020bcf  mov     ebx, 0C0000095h
0x140020bd4  mov     rcx, rdi
0x140020bd7  call    AiFree
0x140020bdc  test    ebx, ebx
0x140020bde  js      short loc_140020BF1
0x140020be0  cmp     qword ptr [r15], 0
0x140020be4  jz      short loc_140020BEC
0x140020be6  cmp     dword ptr [r14], 0
0x140020bea  jnz     short loc_140020BF1
0x140020bec  mov     ebx, 0C0000225h
0x140020bf1  mov     eax, ebx
0x140020bf3  jmp     short loc_140020BFA
0x140020bf5  mov     eax, 0C0000017h
0x140020bfa  mov     rcx, [rsp+0E8h+var_50]
0x140020c02  xor     rcx, rsp; StackCookie
0x140020c05  call    __security_check_cookie
0x140020c0a  add     rsp, 0A8h
0x140020c11  pop     r15
0x140020c13  pop     r14
0x140020c15  pop     r13
0x140020c17  pop     r12
0x140020c19  pop     rdi
0x140020c1a  pop     rsi
0x140020c1b  pop     rbp
0x140020c1c  pop     rbx
0x140020c1d  retn
```
