# Wow64NtCreateKey

- ea: `0x1800719b8`
- end: `0x180071c73`
- name: `Wow64NtCreateKey`
- size: `699`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID P, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006d3f0`
- `0x18006d4fc`

## callees

- `0x180026f6c`
- `0x1800719b8`
- `0x180071c7c`

## import_xrefs

- `ntdll!NtClose` at `0x180071b47`
- `ntdll!NtClose` at `0x180071bd1`
- `ntdll!NtClose` at `0x180071c46`
- `ntdll!NtClose` at `0x180071b47`
- `ntdll!NtClose` at `0x180071bd1`
- `ntdll!NtClose` at `0x180071c46`
- `ntdll!RtlFreeHeap` at `0x180071bf9`
- `ntdll!RtlFreeHeap` at `0x180071bf9`
- `ntdll!NtOpenKeyEx` at `0x180071a9d`
- `ntdll!NtOpenKeyEx` at `0x180071a9d`
- `ntdll!NtSetInformationKey` at `0x180071c30`
- `ntdll!NtSetInformationKey` at `0x180071c30`

## pseudocode

```c
__int64 __fastcall Wow64NtCreateKey(HANDLE *a1, int a2, __int128 *a3, int a4, PVOID P, unsigned int a6)
{
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v9; // xmm0
  __int64 result; // rax
  int v11; // edx
  int v12; // r9d
  unsigned int v13; // r15d
  int KeyInternal; // ebx
  int v15; // r9d
  __int64 v16; // rax
  unsigned int v17; // esi
  __int16 v18; // di
  int v19; // edx
  __int16 v20; // r14
  _WORD *v21; // rsi
  __int16 v22; // r14
  _WORD *v23; // rax
  __int16 v24; // ax
  __int16 v25; // di
  NTSTATUS v26; // edi
  __int64 v27; // [rsp+20h] [rbp-60h]
  __int64 v28; // [rsp+20h] [rbp-60h]
  __int64 v29; // [rsp+40h] [rbp-40h] BYREF
  __int16 v30; // [rsp+48h] [rbp-38h]
  char v31; // [rsp+4Ah] [rbp-36h]
  HANDLE Handle[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v33; // [rsp+60h] [rbp-20h]
  __int128 v34; // [rsp+70h] [rbp-10h]
  int KeySetInformation; // [rsp+C8h] [rbp+48h] BYREF
  HANDLE KeyHandle; // [rsp+D0h] [rbp+50h] BYREF
  int v37; // [rsp+D8h] [rbp+58h] BYREF

  v37 = a4;
  KeySetInformation = a2;
  v6 = *a3;
  v7 = a3[1];
  v29 = 0;
  v30 = 0;
  v31 = 0;
  *(_OWORD *)Handle = v6;
  v9 = a3[2];
  P = 0;
  v34 = v9;
  KeySetInformation = 0;
  v33 = v7;
  KeyHandle = 0;
  LOBYTE(v37) = 0;
  result = ConstructKernelKeyPath(
             0x2000000,
             (unsigned int)Handle,
             (unsigned int)&KeySetInformation,
             (unsigned int)&v29,
             (__int64)&v37,
             (__int64)&P);
  if ( (int)result < 0 )
    return result;
  v13 = a6;
  KeyInternal = Wow64pNtCreateKeyInternal((unsigned int)&KeyHandle, v11, (unsigned int)Handle, v12, v27, a6);
  if ( KeyInternal == -1073741772 && (_BYTE)v29 && WORD2(v29) )
  {
    v16 = v33;
    v17 = WORD1(v29);
    v18 = *(_WORD *)v33;
    if ( !WORD1(v29) )
    {
      KeyInternal = 0;
LABEL_9:
      v19 = 2;
      v20 = WORD2(v29);
      v21 = (_WORD *)(*(_QWORD *)(v16 + 8) + 2LL);
      *(_QWORD *)(v16 + 8) = v21;
      v22 = v20 - 2;
      *(_WORD *)(v33 + 2) -= 2;
      while ( v22 )
      {
        do
        {
          if ( *v21 == 92 )
            break;
          ++v21;
          v22 -= 2;
        }
        while ( v22 );
        *(_WORD *)v33 = 2 * ((__int64)(unsigned int)((_DWORD)v21 - *(_DWORD *)(v33 + 8)) >> 1);
        KeyInternal = Wow64pNtCreateKeyInternal((unsigned int)&KeyHandle, 2, (unsigned int)Handle, v15, v28, v13);
        if ( Handle[1] )
        {
          NtClose(Handle[1]);
          Handle[1] = 0;
        }
        if ( KeyInternal < 0 )
          break;
        v23 = v21 + 1;
        v19 = 2;
        if ( !v22 )
          v23 = v21;
        v21 = v23;
        *(_QWORD *)(v33 + 8) = v23;
        Handle[1] = KeyHandle;
        v24 = v22 - 2;
        if ( !v22 )
          v24 = 0;
        v22 = v24;
      }
      if ( KeyInternal >= 0 )
      {
        v25 = v18 - WORD2(v29);
        if ( v25 )
        {
          *(_WORD *)v33 = v25;
          KeyInternal = Wow64pNtCreateKeyInternal((unsigned int)&KeyHandle, v19, (unsigned int)Handle, v15, v28, v13);
          if ( Handle[1] )
          {
            NtClose(Handle[1]);
            Handle[1] = 0;
          }
        }
      }
      goto LABEL_25;
    }
    *(_WORD *)v33 = WORD1(v29);
    KeyInternal = NtOpenKeyEx(&KeyHandle, 0x2000000, Handle, v13);
    if ( KeyInternal >= 0 )
    {
      v18 -= v17;
      *(_QWORD *)(v33 + 8) += 2 * ((unsigned __int64)v17 >> 1);
      Handle[1] = KeyHandle;
      v16 = v33;
      goto LABEL_9;
    }
  }
LABEL_25:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( KeyInternal >= 0 )
  {
    if ( (_BYTE)v37 )
    {
      if ( KeySetInformation )
      {
        KeySetInformation &= 0xF01u;
        v26 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
        if ( v26 < 0 )
        {
          NtClose(KeyHandle);
          return (unsigned int)v26;
        }
      }
    }
    *a1 = KeyHandle;
  }
  return (unsigned int)KeyInternal;
}

```

## disassembly

```asm
0x1800719b8  mov     [rsp-38h+arg_18], r9d
0x1800719bd  mov     [rsp-38h+KeySetInformation], edx
0x1800719c1  push    rbp
0x1800719c2  push    rbx
0x1800719c3  push    rsi
0x1800719c4  push    rdi
0x1800719c5  push    r13
0x1800719c7  push    r14
0x1800719c9  push    r15
0x1800719cb  mov     rbp, rsp
0x1800719ce  sub     rsp, 80h
0x1800719d5  movups  xmm0, xmmword ptr [r8]
0x1800719d9  xor     eax, eax
0x1800719db  xor     r14d, r14d
0x1800719de  movups  xmm1, xmmword ptr [r8+10h]
0x1800719e3  mov     [rbp+var_40], rax
0x1800719e7  lea     r9, [rbp+var_40]
0x1800719eb  mov     [rbp+var_38], ax
0x1800719ef  lea     rdx, [rbp+Handle]
0x1800719f3  mov     [rbp+var_36], al
0x1800719f6  mov     r13, rcx
0x1800719f9  movups  xmmword ptr [rbp+Handle], xmm0
0x1800719fd  lea     rax, [rbp+P]
0x180071a01  mov     ecx, 2000000h
0x180071a06  movups  xmm0, xmmword ptr [r8+20h]
0x180071a0b  mov     [rsp+80h+var_58], rax
0x180071a10  lea     r8, [rbp+KeySetInformation]
0x180071a14  lea     rax, [rbp+arg_18]
0x180071a18  mov     [rbp+P], r14
0x180071a1c  movups  [rbp+var_10], xmm0
0x180071a20  mov     [rbp+KeySetInformation], r14d
0x180071a24  movups  [rbp+var_20], xmm1
0x180071a28  mov     [rbp+KeyHandle], r14
0x180071a2c  mov     byte ptr [rbp+arg_18], r14b
0x180071a30  mov     [rsp+80h+var_60], rax
0x180071a35  call    ConstructKernelKeyPath
0x180071a3a  test    eax, eax
0x180071a3c  js      loc_180071C60
0x180071a42  mov     r15d, [rbp+arg_28]
0x180071a46  lea     r8, [rbp+Handle]
0x180071a4a  lea     rcx, [rbp+KeyHandle]
0x180071a4e  mov     dword ptr [rsp+80h+var_58], r15d
0x180071a53  call    Wow64pNtCreateKeyInternal
0x180071a58  mov     ebx, eax
0x180071a5a  cmp     eax, 0C0000034h
0x180071a5f  jnz     loc_180071BE1
0x180071a65  cmp     byte ptr [rbp+var_40], r14b
0x180071a69  jz      loc_180071BE1
0x180071a6f  cmp     word ptr [rbp+var_40+4], r14w
0x180071a74  jz      loc_180071BE1
0x180071a7a  mov     rax, qword ptr [rbp+var_20]
0x180071a7e  movzx   esi, word ptr [rbp+var_40+2]
0x180071a82  movzx   edi, word ptr [rax]
0x180071a85  test    si, si
0x180071a88  jz      short loc_180071AD4
0x180071a8a  mov     r9d, r15d
0x180071a8d  mov     [rax], si
0x180071a90  lea     r8, [rbp+Handle]
0x180071a94  mov     edx, 2000000h
0x180071a99  lea     rcx, [rbp+KeyHandle]
0x180071a9d  call    cs:__imp_NtOpenKeyEx
0x180071aa4  nop     dword ptr [rax+rax+00h]
0x180071aa9  mov     ebx, eax
0x180071aab  test    eax, eax
0x180071aad  js      loc_180071BE1
0x180071ab3  mov     rcx, qword ptr [rbp+var_20]
0x180071ab7  mov     eax, esi
0x180071ab9  shr     rax, 1
0x180071abc  sub     di, si
0x180071abf  add     rax, rax
0x180071ac2  add     [rcx+8], rax
0x180071ac6  mov     rax, [rbp+KeyHandle]
0x180071aca  mov     [rbp+Handle+8], rax
0x180071ace  mov     rax, qword ptr [rbp+var_20]
0x180071ad2  jmp     short loc_180071AD7
0x180071ad4  mov     ebx, r14d
0x180071ad7  mov     rsi, [rax+8]
0x180071adb  mov     edx, 2
0x180071ae0  movzx   r14d, word ptr [rbp+var_40+4]
0x180071ae5  add     rsi, rdx
0x180071ae8  mov     [rax+8], rsi
0x180071aec  sub     r14w, dx
0x180071af0  mov     rax, qword ptr [rbp+var_20]
0x180071af4  mov     r8d, 0FFFEh
0x180071afa  add     [rax+2], r8w
0x180071aff  test    r14w, r14w
0x180071b03  jz      loc_180071BA0
0x180071b09  cmp     word ptr [rsi], 5Ch ; '\'
0x180071b0d  jz      short loc_180071B18
0x180071b0f  add     rsi, rdx
0x180071b12  add     r14w, r8w
0x180071b16  jnz     short loc_180071B09
0x180071b18  mov     rax, qword ptr [rbp+var_20]
0x180071b1c  lea     r8, [rbp+Handle]
0x180071b20  mov     ecx, esi
0x180071b22  mov     dword ptr [rsp+80h+var_58], r15d
0x180071b27  sub     ecx, [rax+8]
0x180071b2a  sar     rcx, 1
0x180071b2d  add     cx, cx
0x180071b30  mov     [rax], cx
0x180071b33  lea     rcx, [rbp+KeyHandle]
0x180071b37  call    Wow64pNtCreateKeyInternal
0x180071b3c  mov     rcx, [rbp+Handle+8]; Handle
0x180071b40  mov     ebx, eax
0x180071b42  test    rcx, rcx
0x180071b45  jz      short loc_180071B59
0x180071b47  call    cs:__imp_NtClose
0x180071b4e  nop     dword ptr [rax+rax+00h]
0x180071b53  xor     ecx, ecx
0x180071b55  mov     [rbp+Handle+8], rcx
0x180071b59  test    ebx, ebx
0x180071b5b  js      short loc_180071BA0
0x180071b5d  test    r14w, r14w
0x180071b61  lea     rax, [rsi+2]
0x180071b65  mov     edx, 2
0x180071b6a  mov     r8d, 0FFFEh
0x180071b70  cmovz   rax, rsi
0x180071b74  mov     rsi, rax
0x180071b77  mov     rax, qword ptr [rbp+var_20]
0x180071b7b  mov     [rax+8], rsi
0x180071b7f  mov     rax, [rbp+KeyHandle]
0x180071b83  mov     [rbp+Handle+8], rax
0x180071b87  movzx   eax, r14w
0x180071b8b  sub     ax, dx
0x180071b8e  test    r14w, r14w
0x180071b92  cmovz   ax, r14w
0x180071b97  movzx   r14d, ax
0x180071b9b  jmp     loc_180071AFF
0x180071ba0  xor     r14d, r14d
0x180071ba3  test    ebx, ebx
0x180071ba5  js      short loc_180071BE1
0x180071ba7  sub     di, word ptr [rbp+var_40+4]
0x180071bab  jz      short loc_180071BE1
0x180071bad  mov     rax, qword ptr [rbp+var_20]
0x180071bb1  lea     r8, [rbp+Handle]
0x180071bb5  lea     rcx, [rbp+KeyHandle]
0x180071bb9  mov     dword ptr [rsp+80h+var_58], r15d
0x180071bbe  mov     [rax], di
0x180071bc1  call    Wow64pNtCreateKeyInternal
0x180071bc6  mov     rcx, [rbp+Handle+8]; Handle
0x180071bca  mov     ebx, eax
0x180071bcc  test    rcx, rcx
0x180071bcf  jz      short loc_180071BE1
0x180071bd1  call    cs:__imp_NtClose
0x180071bd8  nop     dword ptr [rax+rax+00h]
0x180071bdd  mov     [rbp+Handle+8], r14
0x180071be1  mov     r8, [rbp+P]; P
0x180071be5  test    r8, r8
0x180071be8  jz      short loc_180071C05
0x180071bea  mov     rcx, gs:60h
0x180071bf3  xor     edx, edx; Flags
0x180071bf5  mov     rcx, [rcx+30h]; HeapHandle
0x180071bf9  call    cs:__imp_RtlFreeHeap
0x180071c00  nop     dword ptr [rax+rax+00h]
0x180071c05  test    ebx, ebx
0x180071c07  js      short loc_180071C5E
0x180071c09  cmp     byte ptr [rbp+arg_18], r14b
0x180071c0d  jz      short loc_180071C56
0x180071c0f  mov     eax, [rbp+KeySetInformation]
0x180071c12  test    eax, eax
0x180071c14  jz      short loc_180071C56
0x180071c16  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180071c1a  lea     r8, [rbp+KeySetInformation]; KeySetInformation
0x180071c1e  mov     r9d, 4; KeySetInformationLength
0x180071c24  and     eax, 0F01h
0x180071c29  mov     [rbp+KeySetInformation], eax
0x180071c2c  lea     edx, [r9+1]; KeySetInformationClass
0x180071c30  call    cs:__imp_NtSetInformationKey
0x180071c37  nop     dword ptr [rax+rax+00h]
0x180071c3c  mov     edi, eax
0x180071c3e  test    eax, eax
0x180071c40  jns     short loc_180071C56
0x180071c42  mov     rcx, [rbp+KeyHandle]; Handle
0x180071c46  call    cs:__imp_NtClose
0x180071c4d  nop     dword ptr [rax+rax+00h]
0x180071c52  mov     eax, edi
0x180071c54  jmp     short loc_180071C60
0x180071c56  mov     rax, [rbp+KeyHandle]
0x180071c5a  mov     [r13+0], rax
0x180071c5e  mov     eax, ebx
0x180071c60  add     rsp, 80h
0x180071c67  pop     r15
0x180071c69  pop     r14
0x180071c6b  pop     r13
0x180071c6d  pop     rdi
0x180071c6e  pop     rsi
0x180071c6f  pop     rbx
0x180071c70  pop     rbp
0x180071c71  retn
```
