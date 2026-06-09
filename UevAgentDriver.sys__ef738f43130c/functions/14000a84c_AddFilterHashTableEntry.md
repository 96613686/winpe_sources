# AddFilterHashTableEntry

- ea: `0x14000a84c`
- end: `0x14000a8f9`
- name: `AddFilterHashTableEntry`
- size: `173`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(__int64), __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b160`

## callees

- `0x140001118`
- `0x1400015c0`
- `0x140001a70`
- `0x14000a84c`

## pseudocode

```c
__int64 __fastcall AddFilterHashTableEntry(__int64 (__fastcall *a1)(__int64), __int64 a2, __int64 a3)
{
  __int64 (__fastcall **v3)(__int64); // rsi
  __int64 v6; // rcx
  int v7; // edi
  __int64 (__fastcall *v8)(__int64); // rbx
  unsigned int v9; // eax
  __int64 (__fastcall *v11)(__int64); // [rsp+40h] [rbp+8h] BYREF

  v11 = a1;
  v3 = (__int64 (__fastcall **)(__int64))P;
  DbgTrace(2, "UevFilter.AddHandleHashTableEntry: Entry\n");
  if ( v3 )
  {
    v11 = 0;
    v7 = AllocateGenericBuffer(v6, 24, &v11);
    if ( v7 >= 0 )
    {
      v8 = v11;
      *((_QWORD *)v11 + 1) = a2;
      *((_QWORD *)v8 + 2) = a3;
      v9 = (*v3)(a2);
      *(_QWORD *)v8 = v3[v9 + 3];
      v3[v9 + 3] = v8;
    }
  }
  else
  {
    v7 = -1073741811;
  }
  DbgTrace(2, "UevFilter.AddHandleHashTableEntry: Exit\n");
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a84c  mov     [rsp+arg_8], rbx
0x14000a851  mov     [rsp+arg_10], rbp
0x14000a856  mov     [rsp+arg_0], rcx
0x14000a85b  push    rsi
0x14000a85c  push    rdi
0x14000a85d  push    r14
0x14000a85f  sub     rsp, 20h
0x14000a863  mov     rsi, cs:P
0x14000a86a  mov     rbp, rdx
0x14000a86d  lea     rdx, aUevfilterAddha_0; "UevFilter.AddHandleHashTableEntry: Entr"...
0x14000a874  mov     ecx, 2
0x14000a879  mov     r14, r8
0x14000a87c  call    DbgTrace
0x14000a881  test    rsi, rsi
0x14000a884  jz      short loc_14000A8CD
0x14000a886  lea     r8, [rsp+38h+arg_0]
0x14000a88b  mov     [rsp+38h+arg_0], 0
0x14000a894  mov     edx, 18h
0x14000a899  call    AllocateGenericBuffer
0x14000a89e  mov     edi, eax
0x14000a8a0  test    eax, eax
0x14000a8a2  js      short loc_14000A8D2
0x14000a8a4  mov     rbx, [rsp+38h+arg_0]
0x14000a8a9  mov     rcx, rbp
0x14000a8ac  mov     [rbx+8], rbp
0x14000a8b0  mov     [rbx+10h], r14
0x14000a8b4  mov     rax, [rsi]
0x14000a8b7  call    _guard_dispatch_icall
0x14000a8bc  mov     edx, eax
0x14000a8be  mov     rcx, [rsi+rdx*8+18h]
0x14000a8c3  mov     [rbx], rcx
0x14000a8c6  mov     [rsi+rdx*8+18h], rbx
0x14000a8cb  jmp     short loc_14000A8D2
0x14000a8cd  mov     edi, 0C000000Dh
0x14000a8d2  lea     rdx, aUevfilterAddha; "UevFilter.AddHandleHashTableEntry: Exit"...
0x14000a8d9  mov     ecx, 2
0x14000a8de  call    DbgTrace
0x14000a8e3  mov     rbx, [rsp+38h+arg_8]
0x14000a8e8  mov     eax, edi
0x14000a8ea  mov     rbp, [rsp+38h+arg_10]
0x14000a8ef  add     rsp, 20h
0x14000a8f3  pop     r14
0x14000a8f5  pop     rdi
0x14000a8f6  pop     rsi
0x14000a8f7  retn
```
