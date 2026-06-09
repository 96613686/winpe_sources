# Wow64NtCreateKey

- ea: `0x180064a10`
- end: `0x180064ca6`
- name: `Wow64NtCreateKey`
- size: `662`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID P, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800609d8`
- `0x180060ad4`

## callees

- `0x180024710`
- `0x180064a10`
- `0x180064cac`

## import_xrefs

- `ntdll!NtClose` at `0x180064b99`
- `ntdll!NtClose` at `0x180064c1d`
- `ntdll!NtClose` at `0x180064c80`
- `ntdll!NtClose` at `0x180064b99`
- `ntdll!NtClose` at `0x180064c1d`
- `ntdll!NtClose` at `0x180064c80`
- `ntdll!RtlFreeHeap` at `0x180064c3f`
- `ntdll!RtlFreeHeap` at `0x180064c3f`
- `ntdll!NtOpenKeyEx` at `0x180064af5`
- `ntdll!NtOpenKeyEx` at `0x180064af5`
- `ntdll!NtSetInformationKey` at `0x180064c70`
- `ntdll!NtSetInformationKey` at `0x180064c70`

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
0x180064a10  mov     [rsp-38h+arg_18], r9d
0x180064a15  mov     [rsp-38h+KeySetInformation], edx
0x180064a19  push    rbp
0x180064a1a  push    rbx
0x180064a1b  push    rsi
0x180064a1c  push    rdi
0x180064a1d  push    r13
0x180064a1f  push    r14
0x180064a21  push    r15
0x180064a23  mov     rbp, rsp
0x180064a26  sub     rsp, 80h
0x180064a2d  movups  xmm0, xmmword ptr [r8]
0x180064a31  xor     eax, eax
0x180064a33  xor     r14d, r14d
0x180064a36  movups  xmm1, xmmword ptr [r8+10h]
0x180064a3b  mov     [rbp+var_40], rax
0x180064a3f  lea     r9, [rbp+var_40]
0x180064a43  mov     [rbp+var_38], ax
0x180064a47  lea     rdx, [rbp+Handle]
0x180064a4b  mov     [rbp+var_36], al
0x180064a4e  mov     r13, rcx
0x180064a51  movups  xmmword ptr [rbp+Handle], xmm0
0x180064a55  lea     rax, [rbp+P]
0x180064a59  mov     ecx, 2000000h
0x180064a5e  movups  xmm0, xmmword ptr [r8+20h]
0x180064a63  mov     [rsp+80h+var_58], rax
0x180064a68  lea     r8, [rbp+KeySetInformation]
0x180064a6c  lea     rax, [rbp+arg_18]
0x180064a70  mov     [rbp+P], r14
0x180064a74  movups  [rbp+var_10], xmm0
0x180064a78  mov     [rbp+KeySetInformation], r14d
0x180064a7c  movups  [rbp+var_20], xmm1
0x180064a80  mov     [rbp+KeyHandle], r14
0x180064a84  mov     byte ptr [rbp+arg_18], r14b
0x180064a88  mov     [rsp+80h+var_60], rax
0x180064a8d  call    ConstructKernelKeyPath
0x180064a92  test    eax, eax
0x180064a94  js      loc_180064C94
0x180064a9a  mov     r15d, [rbp+arg_28]
0x180064a9e  lea     r8, [rbp+Handle]
0x180064aa2  lea     rcx, [rbp+KeyHandle]
0x180064aa6  mov     dword ptr [rsp+80h+var_58], r15d
0x180064aab  call    Wow64pNtCreateKeyInternal
0x180064ab0  mov     ebx, eax
0x180064ab2  cmp     eax, 0C0000034h
0x180064ab7  jnz     loc_180064C27
0x180064abd  cmp     byte ptr [rbp+var_40], r14b
0x180064ac1  jz      loc_180064C27
0x180064ac7  cmp     word ptr [rbp+var_40+4], r14w
0x180064acc  jz      loc_180064C27
0x180064ad2  mov     rax, qword ptr [rbp+var_20]
0x180064ad6  movzx   esi, word ptr [rbp+var_40+2]
0x180064ada  movzx   edi, word ptr [rax]
0x180064add  test    si, si
0x180064ae0  jz      short loc_180064B26
0x180064ae2  mov     r9d, r15d
0x180064ae5  mov     [rax], si
0x180064ae8  lea     r8, [rbp+Handle]
0x180064aec  mov     edx, 2000000h
0x180064af1  lea     rcx, [rbp+KeyHandle]
0x180064af5  call    cs:__imp_NtOpenKeyEx
0x180064afb  mov     ebx, eax
0x180064afd  test    eax, eax
0x180064aff  js      loc_180064C27
0x180064b05  mov     rcx, qword ptr [rbp+var_20]
0x180064b09  mov     eax, esi
0x180064b0b  shr     rax, 1
0x180064b0e  sub     di, si
0x180064b11  add     rax, rax
0x180064b14  add     [rcx+8], rax
0x180064b18  mov     rax, [rbp+KeyHandle]
0x180064b1c  mov     [rbp+Handle+8], rax
0x180064b20  mov     rax, qword ptr [rbp+var_20]
0x180064b24  jmp     short loc_180064B29
0x180064b26  mov     ebx, r14d
0x180064b29  mov     rsi, [rax+8]
0x180064b2d  mov     edx, 2
0x180064b32  movzx   r14d, word ptr [rbp+var_40+4]
0x180064b37  add     rsi, rdx
0x180064b3a  mov     [rax+8], rsi
0x180064b3e  sub     r14w, dx
0x180064b42  mov     rax, qword ptr [rbp+var_20]
0x180064b46  mov     r8d, 0FFFEh
0x180064b4c  add     [rax+2], r8w
0x180064b51  test    r14w, r14w
0x180064b55  jz      loc_180064BEC
0x180064b5b  cmp     word ptr [rsi], 5Ch ; '\'
0x180064b5f  jz      short loc_180064B6A
0x180064b61  add     rsi, rdx
0x180064b64  add     r14w, r8w
0x180064b68  jnz     short loc_180064B5B
0x180064b6a  mov     rax, qword ptr [rbp+var_20]
0x180064b6e  lea     r8, [rbp+Handle]
0x180064b72  mov     ecx, esi
0x180064b74  mov     dword ptr [rsp+80h+var_58], r15d
0x180064b79  sub     ecx, [rax+8]
0x180064b7c  sar     rcx, 1
0x180064b7f  add     cx, cx
0x180064b82  mov     [rax], cx
0x180064b85  lea     rcx, [rbp+KeyHandle]
0x180064b89  call    Wow64pNtCreateKeyInternal
0x180064b8e  mov     rcx, [rbp+Handle+8]; Handle
0x180064b92  mov     ebx, eax
0x180064b94  test    rcx, rcx
0x180064b97  jz      short loc_180064BA5
0x180064b99  call    cs:__imp_NtClose
0x180064b9f  xor     ecx, ecx
0x180064ba1  mov     [rbp+Handle+8], rcx
0x180064ba5  test    ebx, ebx
0x180064ba7  js      short loc_180064BEC
0x180064ba9  test    r14w, r14w
0x180064bad  lea     rax, [rsi+2]
0x180064bb1  mov     edx, 2
0x180064bb6  mov     r8d, 0FFFEh
0x180064bbc  cmovz   rax, rsi
0x180064bc0  mov     rsi, rax
0x180064bc3  mov     rax, qword ptr [rbp+var_20]
0x180064bc7  mov     [rax+8], rsi
0x180064bcb  mov     rax, [rbp+KeyHandle]
0x180064bcf  mov     [rbp+Handle+8], rax
0x180064bd3  movzx   eax, r14w
0x180064bd7  sub     ax, dx
0x180064bda  test    r14w, r14w
0x180064bde  cmovz   ax, r14w
0x180064be3  movzx   r14d, ax
0x180064be7  jmp     loc_180064B51
0x180064bec  xor     r14d, r14d
0x180064bef  test    ebx, ebx
0x180064bf1  js      short loc_180064C27
0x180064bf3  sub     di, word ptr [rbp+var_40+4]
0x180064bf7  jz      short loc_180064C27
0x180064bf9  mov     rax, qword ptr [rbp+var_20]
0x180064bfd  lea     r8, [rbp+Handle]
0x180064c01  lea     rcx, [rbp+KeyHandle]
0x180064c05  mov     dword ptr [rsp+80h+var_58], r15d
0x180064c0a  mov     [rax], di
0x180064c0d  call    Wow64pNtCreateKeyInternal
0x180064c12  mov     rcx, [rbp+Handle+8]; Handle
0x180064c16  mov     ebx, eax
0x180064c18  test    rcx, rcx
0x180064c1b  jz      short loc_180064C27
0x180064c1d  call    cs:__imp_NtClose
0x180064c23  mov     [rbp+Handle+8], r14
0x180064c27  mov     r8, [rbp+P]; P
0x180064c2b  test    r8, r8
0x180064c2e  jz      short loc_180064C45
0x180064c30  mov     rcx, gs:60h
0x180064c39  xor     edx, edx; Flags
0x180064c3b  mov     rcx, [rcx+30h]; HeapHandle
0x180064c3f  call    cs:__imp_RtlFreeHeap
0x180064c45  test    ebx, ebx
0x180064c47  js      short loc_180064C92
0x180064c49  cmp     byte ptr [rbp+arg_18], r14b
0x180064c4d  jz      short loc_180064C8A
0x180064c4f  mov     eax, [rbp+KeySetInformation]
0x180064c52  test    eax, eax
0x180064c54  jz      short loc_180064C8A
0x180064c56  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180064c5a  lea     r8, [rbp+KeySetInformation]; KeySetInformation
0x180064c5e  mov     r9d, 4; KeySetInformationLength
0x180064c64  and     eax, 0F01h
0x180064c69  mov     [rbp+KeySetInformation], eax
0x180064c6c  lea     edx, [r9+1]; KeySetInformationClass
0x180064c70  call    cs:__imp_NtSetInformationKey
0x180064c76  mov     edi, eax
0x180064c78  test    eax, eax
0x180064c7a  jns     short loc_180064C8A
0x180064c7c  mov     rcx, [rbp+KeyHandle]; Handle
0x180064c80  call    cs:__imp_NtClose
0x180064c86  mov     eax, edi
0x180064c88  jmp     short loc_180064C94
0x180064c8a  mov     rax, [rbp+KeyHandle]
0x180064c8e  mov     [r13+0], rax
0x180064c92  mov     eax, ebx
0x180064c94  add     rsp, 80h
0x180064c9b  pop     r15
0x180064c9d  pop     r14
0x180064c9f  pop     r13
0x180064ca1  pop     rdi
0x180064ca2  pop     rsi
0x180064ca3  pop     rbx
0x180064ca4  pop     rbp
0x180064ca5  retn
```
