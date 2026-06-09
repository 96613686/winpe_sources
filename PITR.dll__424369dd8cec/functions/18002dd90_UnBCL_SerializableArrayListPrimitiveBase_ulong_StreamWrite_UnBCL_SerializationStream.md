# UnBCL::_::SerializableArrayListPrimitiveBase<ulong>::StreamWrite(UnBCL::SerializationStream &)

- ea: `0x18002dd90`
- end: `0x18002de96`
- name: `?StreamWrite@?$SerializableArrayListPrimitiveBase@K@_@UnBCL@@UEBAXAEAVSerializationStream@3@@Z`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002dd50`
- `0x18002dd70`

## callees

- `0x18002dd90`
- `0x1800502a7`
- `0x180053010`

## import_xrefs

- `unbcl!?WriteBytes@SerializationStream@UnBCL@@QEAAXPEBEH@Z` at `0x18002de86`
- `unbcl!?WriteBytes@SerializationStream@UnBCL@@QEAAXPEBEH@Z` at `0x18002de86`
- `unbcl!??6SerializationStream@UnBCL@@QEAAAEAV01@AEBH@Z` at `0x18002ddc9`
- `unbcl!??6SerializationStream@UnBCL@@QEAAAEAV01@AEBH@Z` at `0x18002de2b`
- `unbcl!??6SerializationStream@UnBCL@@QEAAAEAV01@AEBH@Z` at `0x18002ddc9`
- `unbcl!??6SerializationStream@UnBCL@@QEAAAEAV01@AEBH@Z` at `0x18002de2b`

## pseudocode

```c
void __fastcall UnBCL::_::SerializableArrayListPrimitiveBase<unsigned long>::StreamWrite(
        __int64 a1,
        UnBCL::SerializationStream *a2)
{
  __int64 v2; // rdi
  __int64 (__fastcall ***v5)(_QWORD); // rcx
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r14
  int (__fastcall ***v10)(_QWORD); // rcx
  __int64 (__fastcall ***v11)(_QWORD); // rcx
  int v12; // ebx
  const unsigned __int8 *v13; // rax
  int v14; // [rsp+60h] [rbp+8h] BYREF

  v2 = a1 - 72;
  v5 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(a1 - 72) + 12LL) + a1 - 72);
  v14 = (**v5)(v5);
  UnBCL::SerializationStream::operator<<(a2, &v14);
  if ( v2 )
  {
    v8 = *(int *)(*(_QWORD *)v2 + 4LL);
    v6 = v8 + a1 - 72;
    v7 = a1 + v8 - 72;
  }
  else
  {
    v6 = 0;
    v7 = 0;
  }
  v9 = _RTDynamicCast_0(
         v7,
         (unsigned int)(v6 - a1 + 72),
         &UnBCL::_::SerializableArrayListPrimitiveBase<unsigned long> `RTTI Type Descriptor',
         &UnBCL::ArrayList<unsigned long> `RTTI Type Descriptor',
         0);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
  UnBCL::SerializationStream::operator<<(a2, &v14);
  v10 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)v2 + 12LL) - 72LL);
  if ( (**v10)(v10) > 0 )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)v2 + 12LL) - 72LL);
    v12 = 4 * (**v11)(v11);
    v13 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 104LL))(v9, 0);
    UnBCL::SerializationStream::WriteBytes(a2, v13, v12);
  }
}

```

## disassembly

```asm
0x18002dd90  push    rbx
0x18002dd92  push    rsi
0x18002dd93  push    rdi
0x18002dd94  push    r14
0x18002dd96  sub     rsp, 38h
0x18002dd9a  lea     rdi, [rcx-48h]
0x18002dd9e  mov     rbx, rcx
0x18002dda1  mov     rax, [rdi]
0x18002dda4  add     rcx, 0FFFFFFFFFFFFFFB8h
0x18002dda8  mov     rsi, rdx
0x18002ddab  movsxd  r8, dword ptr [rax+0Ch]
0x18002ddaf  add     rcx, r8
0x18002ddb2  mov     rax, [rcx]
0x18002ddb5  mov     rax, [rax]
0x18002ddb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddbd  lea     rdx, [rsp+58h+arg_0]
0x18002ddc2  mov     [rsp+58h+arg_0], eax
0x18002ddc6  mov     rcx, rsi
0x18002ddc9  call    cs:__imp_??6SerializationStream@UnBCL@@QEAAAEAV01@AEBH@Z; UnBCL::SerializationStream::operator<<(int const &)
0x18002ddcf  test    rdi, rdi
0x18002ddd2  jnz     short loc_18002DDDA
0x18002ddd4  xor     edx, edx
0x18002ddd6  xor     ecx, ecx
0x18002ddd8  jmp     short loc_18002DDED
0x18002ddda  mov     rax, [rdi]
0x18002dddd  lea     edx, [rbx-48h]
0x18002dde0  movsxd  rcx, dword ptr [rax+4]
0x18002dde4  add     edx, ecx
0x18002dde6  add     rcx, 0FFFFFFFFFFFFFFB8h
0x18002ddea  add     rcx, rbx
0x18002dded  sub     edx, ebx
0x18002ddef  mov     [rsp+58h+var_38], 0
0x18002ddf7  add     edx, 48h ; 'H'
0x18002ddfa  lea     r9, ??_R0?AV?$ArrayList@K@UnBCL@@@8; UnBCL::ArrayList<ulong> `RTTI Type Descriptor'
0x18002de01  lea     r8, ??_R0?AV?$SerializableArrayListPrimitiveBase@K@_@UnBCL@@@8; UnBCL::_::SerializableArrayListPrimitiveBase<ulong> `RTTI Type Descriptor'
0x18002de08  call    __RTDynamicCast_0
0x18002de0d  mov     r14, rax
0x18002de10  mov     rcx, [rax]
0x18002de13  mov     rax, [rcx+20h]
0x18002de17  mov     rcx, r14
0x18002de1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de1f  lea     rdx, [rsp+58h+arg_0]
0x18002de24  mov     [rsp+58h+arg_0], eax
0x18002de28  mov     rcx, rsi
0x18002de2b  call    cs:__imp_??6SerializationStream@UnBCL@@QEAAAEAV01@AEBH@Z; UnBCL::SerializationStream::operator<<(int const &)
0x18002de31  mov     rcx, [rdi]
0x18002de34  movsxd  rcx, dword ptr [rcx+0Ch]
0x18002de38  add     rcx, 0FFFFFFFFFFFFFFB8h
0x18002de3c  add     rcx, rbx
0x18002de3f  mov     rdx, [rcx]
0x18002de42  mov     rax, [rdx]
0x18002de45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de4a  test    eax, eax
0x18002de4c  jle     short loc_18002DE8C
0x18002de4e  mov     rax, [rdi]
0x18002de51  movsxd  rcx, dword ptr [rax+0Ch]
0x18002de55  add     rcx, 0FFFFFFFFFFFFFFB8h
0x18002de59  add     rcx, rbx
0x18002de5c  mov     rax, [rcx]
0x18002de5f  mov     rax, [rax]
0x18002de62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de67  mov     ebx, eax
0x18002de69  xor     edx, edx
0x18002de6b  mov     rax, [r14]
0x18002de6e  mov     rcx, r14
0x18002de71  shl     ebx, 2
0x18002de74  mov     rax, [rax+68h]
0x18002de78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de7d  mov     rdx, rax
0x18002de80  mov     r8d, ebx
0x18002de83  mov     rcx, rsi
0x18002de86  call    cs:__imp_?WriteBytes@SerializationStream@UnBCL@@QEAAXPEBEH@Z; UnBCL::SerializationStream::WriteBytes(uchar const *,int)
0x18002de8c  add     rsp, 38h
0x18002de90  pop     r14
0x18002de92  pop     rdi
0x18002de93  pop     rsi
0x18002de94  pop     rbx
0x18002de95  retn
```
