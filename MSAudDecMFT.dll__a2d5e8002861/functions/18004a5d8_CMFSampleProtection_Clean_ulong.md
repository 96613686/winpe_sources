# CMFSampleProtection::Clean(ulong)

- ea: `0x18004a5d8`
- end: `0x18004a6f0`
- name: `?Clean@CMFSampleProtection@@QEAAJK@Z`
- size: `280`
- prototype: `__int64 __fastcall(CMFSampleProtection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003137c`
- `0x18005dedc`

## callees

- `0x18004a5d8`
- `0x18004a6f8`
- `0x18004a7cc`
- `0x18004d320`
- `0x18004dd14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a6a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a6a9`

## pseudocode

```c
__int64 __fastcall CMFSampleProtection::Clean(CMFSampleProtection *this, unsigned int a2)
{
  __int64 v2; // rdi
  _BYTE *v5; // rdx
  _BYTE *v6; // r8
  unsigned __int8 v7; // r9
  __int64 v8; // rax
  _DWORD v9[4]; // [rsp+20h] [rbp-138h]
  _BYTE v10[272]; // [rsp+30h] [rbp-128h] BYREF

  v2 = a2;
  memset_0(v10, 0, sizeof(v10));
  if ( (unsigned int)v2 >= 0x10 )
    return 2147942487LL;
  if ( *((_QWORD *)this + v2 + 50) )
  {
    SymCryptRc4Init(v10, (char *)this + 36, 20);
    SymCryptRc4Crypt(v10, (char *)this + 4 * v2 + 528, (char *)this + 4 * v2 + 528, 4);
    v5 = (_BYTE *)*((_QWORD *)this + v2 + 50);
    v9[0] = -1749680893;
    if ( v5 )
    {
      v6 = &v5[*((unsigned int *)this + v2 + 132)];
      if ( v6 >= v5 )
      {
        v7 = 0;
        while ( v5 < v6 )
        {
          v8 = v7;
          v7 = (v7 + 1) & 3;
          *v5++ = *((_BYTE *)v9 + v8);
        }
      }
    }
    CoTaskMemFree(*((LPVOID *)this + v2 + 50));
    *((_DWORD *)this + v2 + 132) = 0;
    *((_QWORD *)this + v2 + 50) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18004a5d8  mov     [rsp+arg_10], rbx
0x18004a5dd  push    rdi
0x18004a5de  sub     rsp, 150h
0x18004a5e5  mov     rax, cs:__security_cookie
0x18004a5ec  xor     rax, rsp
0x18004a5ef  mov     [rsp+158h+var_18], rax
0x18004a5f7  mov     edi, edx
0x18004a5f9  mov     rbx, rcx
0x18004a5fc  xor     edx, edx; Val
0x18004a5fe  lea     rcx, [rsp+158h+var_128]; void *
0x18004a603  mov     r8d, 110h; Size
0x18004a609  call    memset_0
0x18004a60e  cmp     edi, 10h
0x18004a611  jb      short loc_18004A61D
0x18004a613  mov     eax, 80070057h
0x18004a618  jmp     loc_18004A6CE
0x18004a61d  cmp     qword ptr [rbx+rdi*8+190h], 0
0x18004a626  jz      loc_18004A6CC
0x18004a62c  lea     rdx, [rbx+24h]
0x18004a630  mov     r8d, 14h
0x18004a636  lea     rcx, [rsp+158h+var_128]
0x18004a63b  call    SymCryptRc4Init
0x18004a640  lea     rdx, [rbx+210h]
0x18004a647  mov     r9d, 4
0x18004a64d  lea     rdx, [rdx+rdi*4]
0x18004a651  mov     r8, rdx
0x18004a654  lea     rcx, [rsp+158h+var_128]
0x18004a659  call    SymCryptRc4Crypt
0x18004a65e  mov     rdx, [rbx+rdi*8+190h]
0x18004a666  mov     [rsp+158h+var_138], 97B5FD03h
0x18004a66e  test    rdx, rdx
0x18004a671  jz      short loc_18004A6A1
0x18004a673  mov     r8d, [rbx+rdi*4+210h]
0x18004a67b  add     r8, rdx
0x18004a67e  cmp     r8, rdx
0x18004a681  jb      short loc_18004A6A1
0x18004a683  xor     r9b, r9b
0x18004a686  jmp     short loc_18004A69C
0x18004a688  movzx   eax, r9b
0x18004a68c  inc     r9b
0x18004a68f  and     r9b, 3
0x18004a693  mov     cl, byte ptr [rsp+rax+158h+var_138]
0x18004a697  mov     [rdx], cl
0x18004a699  inc     rdx
0x18004a69c  cmp     rdx, r8
0x18004a69f  jb      short loc_18004A688
0x18004a6a1  mov     rcx, [rbx+rdi*8+190h]; pv
0x18004a6a9  call    cs:__imp_CoTaskMemFree
0x18004a6b0  nop     dword ptr [rax+rax+00h]
0x18004a6b5  mov     dword ptr [rbx+rdi*4+210h], 0
0x18004a6c0  mov     qword ptr [rbx+rdi*8+190h], 0
0x18004a6cc  xor     eax, eax
0x18004a6ce  mov     rcx, [rsp+158h+var_18]
0x18004a6d6  xor     rcx, rsp; StackCookie
0x18004a6d9  call    __security_check_cookie
0x18004a6de  mov     rbx, [rsp+158h+arg_10]
0x18004a6e6  add     rsp, 150h
0x18004a6ed  pop     rdi
0x18004a6ee  retn
```
