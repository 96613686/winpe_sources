# BfspIdentifierIsReferenced

- ea: `0x140006b08`
- end: `0x140006ccf`
- name: `BfspIdentifierIsReferenced`
- size: `455`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, unsigned int, _BYTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140006b08`
- `0x1400078f4`

## callees

- `0x140006a14`
- `0x140006b08`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140006c4e`
- `KERNEL32!HeapFree` at `0x140006c4e`
- `KERNEL32!GetProcessHeap` at `0x140006c40`
- `KERNEL32!GetProcessHeap` at `0x140006c40`

## string_xrefs

- `0x140006b5c`: `Failed to open a handle to the object element. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspIdentifierIsReferenced(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        unsigned int a5,
        _BYTE *a6)
{
  void *v7; // rdi
  int v8; // eax
  int IsReferenced; // ebx
  __int64 i; // r15
  unsigned int v11; // ebx
  int BcdElementData; // eax
  int v13; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v16; // edx
  unsigned int v17; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  __int128 v20; // [rsp+48h] [rbp-18h]
  int v21; // [rsp+90h] [rbp+30h]

  v21 = a1;
  v17 = 0;
  Handle = 0;
  *a6 = 0;
  v7 = 0;
  lpMem = 0;
  v20 = 0;
  v8 = BcdOpenObject(a1, a3, &Handle);
  IsReferenced = v8;
  if ( v8 >= 0 )
  {
    for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
    {
      v11 = *(_DWORD *)(a4 + 4 * i);
      BcdElementData = BfspGetBcdElementData((__int64)Handle, v11, &lpMem, &v17);
      v7 = lpMem;
      if ( BcdElementData >= 0 )
      {
        v13 = v11 & 0xF000000;
        if ( v13 == 0x1000000 )
        {
          if ( *(_QWORD *)((char *)lpMem + 4) == *a2 && *(_QWORD *)((char *)lpMem + 12) == a2[1] )
            goto LABEL_16;
          if ( *(_OWORD *)((char *)lpMem + 4) != v20 )
          {
            IsReferenced = BfspIdentifierIsReferenced(
                             v21,
                             (_DWORD)a2,
                             (int)lpMem + 4,
                             (unsigned int)&ReferenceElementListAdditionalOptionsRecurse,
                             3,
                             (__int64)a6);
            if ( IsReferenced < 0 || *a6 )
              goto LABEL_18;
          }
        }
        else if ( v13 == 50331648 )
        {
          if ( v17 != 16 )
            goto LABEL_31;
          if ( *(_QWORD *)lpMem == *a2 && *((_QWORD *)lpMem + 1) == a2[1] )
            goto LABEL_16;
        }
        else
        {
          if ( v13 != 0x4000000 || (v17 & 0xF) != 0 )
          {
LABEL_31:
            IsReferenced = -1073741811;
            goto LABEL_18;
          }
          v16 = 0;
          if ( v17 >> 4 )
          {
            while ( *((_QWORD *)lpMem + 2 * v16) != *a2 || *((_QWORD *)lpMem + 2 * v16 + 1) != a2[1] )
            {
              if ( ++v16 >= v17 >> 4 )
                goto LABEL_29;
            }
LABEL_16:
            *a6 = 1;
            break;
          }
        }
      }
LABEL_29:
      ;
    }
    IsReferenced = 0;
LABEL_18:
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
  }
  else
  {
    BfspLogMessage(4, L"Failed to open a handle to the object element. Status = [%x]", (unsigned int)v8);
  }
  if ( Handle )
    BcdCloseObject(Handle);
  return (unsigned int)IsReferenced;
}

```

## disassembly

```asm
0x140006b08  mov     [rsp-28h+arg_8], rbx
0x140006b0d  mov     [rsp-28h+arg_18], r9
0x140006b12  mov     [rsp-28h+arg_0], rcx
0x140006b17  push    rbp
0x140006b18  push    rsi
0x140006b19  push    rdi
0x140006b1a  push    r14
0x140006b1c  push    r15
0x140006b1e  mov     rbp, rsp
0x140006b21  sub     rsp, 60h
0x140006b25  mov     rsi, [rbp+arg_28]
0x140006b29  mov     r14, rdx
0x140006b2c  xor     edx, edx
0x140006b2e  mov     rax, r8
0x140006b31  mov     [rbp+var_30], edx
0x140006b34  lea     r8, [rbp+Handle]
0x140006b38  xorps   xmm0, xmm0
0x140006b3b  mov     [rbp+Handle], rdx
0x140006b3f  mov     [rsi], dl
0x140006b41  mov     edi, edx
0x140006b43  mov     [rbp+lpMem], rdx
0x140006b47  mov     rdx, rax
0x140006b4a  movups  [rbp+var_18], xmm0
0x140006b4e  call    BcdOpenObject
0x140006b53  mov     ebx, eax
0x140006b55  test    eax, eax
0x140006b57  jns     short loc_140006B70
0x140006b59  mov     r8d, eax
0x140006b5c  lea     rdx, aFailedToOpenAH_5; "Failed to open a handle to the object e"...
0x140006b63  lea     ecx, [rdi+4]
0x140006b66  call    BfspLogMessage
0x140006b6b  jmp     loc_140006C54
0x140006b70  xor     r15d, r15d
0x140006b73  cmp     [rbp+arg_20], edi
0x140006b76  jbe     loc_140006C39
0x140006b7c  mov     rcx, [rbp+arg_18]
0x140006b80  lea     r9, [rbp+var_30]
0x140006b84  lea     r8, [rbp+lpMem]
0x140006b88  mov     ebx, [rcx+r15*4]
0x140006b8c  mov     edx, ebx
0x140006b8e  mov     rcx, [rbp+Handle]
0x140006b92  call    BfspGetBcdElementData
0x140006b97  mov     rdi, [rbp+lpMem]
0x140006b9b  test    eax, eax
0x140006b9d  js      loc_140006CB3
0x140006ba3  and     ebx, 0F000000h
0x140006ba9  cmp     ebx, 1000000h
0x140006baf  jnz     short loc_140006C0E
0x140006bb1  lea     r8, [rdi+4]
0x140006bb5  mov     rax, [r8]
0x140006bb8  cmp     rax, [r14]
0x140006bbb  jnz     short loc_140006BC7
0x140006bbd  mov     rax, [r8+8]
0x140006bc1  cmp     rax, [r14+8]
0x140006bc5  jz      short loc_140006C36
0x140006bc7  mov     rax, qword ptr [rbp+var_18]
0x140006bcb  cmp     [r8], rax
0x140006bce  jnz     short loc_140006BDE
0x140006bd0  mov     rax, qword ptr [rbp+var_18+8]
0x140006bd4  cmp     [r8+8], rax
0x140006bd8  jz      loc_140006CB3
0x140006bde  mov     rcx, [rbp+arg_0]
0x140006be2  lea     r9, ReferenceElementListAdditionalOptionsRecurse
0x140006be9  mov     [rsp+60h+var_38], rsi
0x140006bee  mov     rdx, r14
0x140006bf1  mov     [rsp+60h+var_40], 3
0x140006bf9  call    BfspIdentifierIsReferenced
0x140006bfe  mov     ebx, eax
0x140006c00  test    eax, eax
0x140006c02  js      short loc_140006C3B
0x140006c04  cmp     byte ptr [rsi], 0
0x140006c07  jnz     short loc_140006C3B
0x140006c09  jmp     loc_140006CB3
0x140006c0e  cmp     ebx, 3000000h
0x140006c14  jnz     short loc_140006C7A
0x140006c16  cmp     [rbp+var_30], 10h
0x140006c1a  jnz     loc_140006CC5
0x140006c20  mov     rax, [rdi]
0x140006c23  cmp     rax, [r14]
0x140006c26  jnz     loc_140006CB3
0x140006c2c  mov     rax, [rdi+8]
0x140006c30  cmp     rax, [r14+8]
0x140006c34  jnz     short loc_140006CB3
0x140006c36  mov     byte ptr [rsi], 1
0x140006c39  xor     ebx, ebx
0x140006c3b  test    rdi, rdi
0x140006c3e  jz      short loc_140006C54
0x140006c40  call    cs:__imp_GetProcessHeap
0x140006c46  mov     r8, rdi; lpMem
0x140006c49  xor     edx, edx; dwFlags
0x140006c4b  mov     rcx, rax; hHeap
0x140006c4e  call    cs:__imp_HeapFree
0x140006c54  cmp     [rbp+Handle], 0
0x140006c59  jz      short loc_140006C64
0x140006c5b  mov     rcx, [rbp+Handle]; Handle
0x140006c5f  call    BcdCloseObject
0x140006c64  mov     eax, ebx
0x140006c66  mov     rbx, [rsp+60h+arg_8]
0x140006c6e  add     rsp, 60h
0x140006c72  pop     r15
0x140006c74  pop     r14
0x140006c76  pop     rdi
0x140006c77  pop     rsi
0x140006c78  pop     rbp
0x140006c79  retn
0x140006c7a  cmp     ebx, 4000000h
0x140006c80  jnz     short loc_140006CC5
0x140006c82  mov     ecx, [rbp+var_30]
0x140006c85  test    cl, 0Fh
0x140006c88  jnz     short loc_140006CC5
0x140006c8a  shr     ecx, 4
0x140006c8d  xor     edx, edx
0x140006c8f  test    ecx, ecx
0x140006c91  jz      short loc_140006CB3
0x140006c93  mov     r8d, edx
0x140006c96  add     r8, r8
0x140006c99  mov     rax, [rdi+r8*8]
0x140006c9d  cmp     rax, [r14]
0x140006ca0  jnz     short loc_140006CAD
0x140006ca2  mov     rax, [rdi+r8*8+8]
0x140006ca7  cmp     rax, [r14+8]
0x140006cab  jz      short loc_140006C36
0x140006cad  inc     edx
0x140006caf  cmp     edx, ecx
0x140006cb1  jb      short loc_140006C93
0x140006cb3  inc     r15d
0x140006cb6  cmp     r15d, [rbp+arg_20]
0x140006cba  jb      loc_140006B7C
0x140006cc0  jmp     loc_140006C39
0x140006cc5  mov     ebx, 0C000000Dh
0x140006cca  jmp     loc_140006C3B
```
