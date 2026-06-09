# UnBCL::_::SerializableArrayListPrimitiveBase<ulong>::StreamRead(UnBCL::SerializationStream &)

- ea: `0x18002da10`
- end: `0x18002db1a`
- name: `?StreamRead@?$SerializableArrayListPrimitiveBase@K@_@UnBCL@@UEAAXAEAVSerializationStream@3@@Z`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d9d0`
- `0x18002d9f0`

## callees

- `0x18002da10`
- `0x1800502a7`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `unbcl!?ReadBytes@SerializationStream@UnBCL@@QEAAXPEAEH@Z` at `0x18002daf7`
- `unbcl!?ReadBytes@SerializationStream@UnBCL@@QEAAXPEAEH@Z` at `0x18002daf7`
- `unbcl!??5SerializationStream@UnBCL@@QEAAAEAV01@AEAH@Z` at `0x18002da44`
- `unbcl!??5SerializationStream@UnBCL@@QEAAAEAV01@AEAH@Z` at `0x18002da5a`
- `unbcl!??5SerializationStream@UnBCL@@QEAAAEAV01@AEAH@Z` at `0x18002da44`
- `unbcl!??5SerializationStream@UnBCL@@QEAAAEAV01@AEAH@Z` at `0x18002da5a`

## pseudocode

```c
void __fastcall UnBCL::_::SerializableArrayListPrimitiveBase<unsigned long>::StreamRead(
        __int64 a1,
        UnBCL::SerializationStream *a2)
{
  int v4; // edx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rsi
  int v8; // ebx
  unsigned __int8 *v9; // rax
  int v10; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-14h] BYREF

  v10 = 0;
  UnBCL::SerializationStream::operator>>(a2, &v10);
  v11 = 0;
  UnBCL::SerializationStream::operator>>(a2, &v11);
  if ( a1 == 72 )
  {
    v4 = 0;
    v5 = 0;
  }
  else
  {
    v6 = *(int *)(*(_QWORD *)(a1 - 72) + 4LL);
    v4 = v6 + a1 - 72;
    v5 = a1 + v6 - 72;
  }
  v7 = _RTDynamicCast_0(
         v5,
         (unsigned int)(v4 - a1 + 72),
         &UnBCL::_::SerializableArrayListPrimitiveBase<unsigned long> `RTTI Type Descriptor',
         &UnBCL::ArrayList<unsigned long> `RTTI Type Descriptor',
         0);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, v11);
  if ( v10 > 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, (unsigned int)v10, 0);
    v8 = 4 * v10;
    v9 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 112LL))(v7, 0);
    UnBCL::SerializationStream::ReadBytes(a2, v9, v8);
  }
}

```

## disassembly

```asm
0x18002da10  mov     [rsp+arg_10], rbx
0x18002da15  mov     [rsp+arg_18], rsi
0x18002da1a  push    rdi
0x18002da1b  sub     rsp, 40h
0x18002da1f  mov     rax, cs:__security_cookie
0x18002da26  xor     rax, rsp
0x18002da29  mov     [rsp+48h+var_10], rax
0x18002da2e  mov     rdi, rdx
0x18002da31  mov     [rsp+48h+var_18], 0
0x18002da39  mov     rbx, rcx
0x18002da3c  lea     rdx, [rsp+48h+var_18]
0x18002da41  mov     rcx, rdi
0x18002da44  call    cs:__imp_??5SerializationStream@UnBCL@@QEAAAEAV01@AEAH@Z; UnBCL::SerializationStream::operator>>(int &)
0x18002da4a  lea     rdx, [rsp+48h+var_14]
0x18002da4f  mov     [rsp+48h+var_14], 0
0x18002da57  mov     rcx, rdi
0x18002da5a  call    cs:__imp_??5SerializationStream@UnBCL@@QEAAAEAV01@AEAH@Z; UnBCL::SerializationStream::operator>>(int &)
0x18002da60  lea     rax, [rbx-48h]
0x18002da64  test    rax, rax
0x18002da67  jnz     short loc_18002DA6F
0x18002da69  xor     edx, edx
0x18002da6b  xor     ecx, ecx
0x18002da6d  jmp     short loc_18002DA82
0x18002da6f  mov     rax, [rax]
0x18002da72  lea     edx, [rbx-48h]
0x18002da75  movsxd  rcx, dword ptr [rax+4]
0x18002da79  add     edx, ecx
0x18002da7b  add     rcx, 0FFFFFFFFFFFFFFB8h
0x18002da7f  add     rcx, rbx
0x18002da82  sub     edx, ebx
0x18002da84  mov     [rsp+48h+var_28], 0
0x18002da8c  add     edx, 48h ; 'H'
0x18002da8f  lea     r9, ??_R0?AV?$ArrayList@K@UnBCL@@@8; UnBCL::ArrayList<ulong> `RTTI Type Descriptor'
0x18002da96  lea     r8, ??_R0?AV?$SerializableArrayListPrimitiveBase@K@_@UnBCL@@@8; UnBCL::_::SerializableArrayListPrimitiveBase<ulong> `RTTI Type Descriptor'
0x18002da9d  call    __RTDynamicCast_0
0x18002daa2  mov     edx, [rsp+48h+var_14]
0x18002daa6  mov     rsi, rax
0x18002daa9  mov     rcx, [rax]
0x18002daac  mov     rax, [rcx+28h]
0x18002dab0  mov     rcx, rsi
0x18002dab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dab8  mov     edx, [rsp+48h+var_18]
0x18002dabc  test    edx, edx
0x18002dabe  jle     short loc_18002DAFD
0x18002dac0  mov     rcx, [rsi]
0x18002dac3  xor     r8d, r8d
0x18002dac6  mov     rax, [rcx+40h]
0x18002daca  mov     rcx, rsi
0x18002dacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dad2  mov     eax, [rsp+48h+var_18]
0x18002dad6  xor     edx, edx
0x18002dad8  mov     rcx, rsi
0x18002dadb  lea     ebx, ds:0[rax*4]
0x18002dae2  mov     rax, [rsi]
0x18002dae5  mov     rax, [rax+70h]
0x18002dae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daee  mov     rdx, rax
0x18002daf1  mov     r8d, ebx
0x18002daf4  mov     rcx, rdi
0x18002daf7  call    cs:__imp_?ReadBytes@SerializationStream@UnBCL@@QEAAXPEAEH@Z; UnBCL::SerializationStream::ReadBytes(uchar *,int)
0x18002dafd  mov     rcx, [rsp+48h+var_10]
0x18002db02  xor     rcx, rsp; StackCookie
0x18002db05  call    __security_check_cookie
0x18002db0a  mov     rbx, [rsp+48h+arg_10]
0x18002db0f  mov     rsi, [rsp+48h+arg_18]
0x18002db14  add     rsp, 40h
0x18002db18  pop     rdi
0x18002db19  retn
```
