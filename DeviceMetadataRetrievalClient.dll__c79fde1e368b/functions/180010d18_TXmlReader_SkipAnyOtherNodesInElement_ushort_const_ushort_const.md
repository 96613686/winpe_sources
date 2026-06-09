# TXmlReader::SkipAnyOtherNodesInElement(ushort const *,ushort const *)

- ea: `0x180010d18`
- end: `0x180010dff`
- name: `?SkipAnyOtherNodesInElement@TXmlReader@@QEAAJPEBG0@Z`
- size: `231`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008544`
- `0x18000913c`
- `0x18000a4c4`
- `0x18000dabc`

## callees

- `0x1800109a4`
- `0x1800109e4`
- `0x180010d18`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::SkipAnyOtherNodesInElement(
        TXmlReader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 result; // rax
  const unsigned __int16 *v7; // rax
  int v8; // r8d
  int v9; // edx
  __int64 v10; // r8
  int v11; // ecx
  int v12; // edx
  __int64 v13; // [rsp+20h] [rbp-18h] BYREF
  __int64 v14; // [rsp+28h] [rbp-10h] BYREF
  enum XmlNodeType v15; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  do
  {
    result = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)this + 104LL))(
               *(_QWORD *)this,
               &v13,
               0);
    if ( (_DWORD)result )
      break;
    v7 = a3;
    do
    {
      v8 = *(const unsigned __int16 *)((char *)v7 + v13 - (_QWORD)a3);
      v9 = *v7 - v8;
      if ( v9 )
        break;
      ++v7;
    }
    while ( v8 );
    if ( !v9 )
    {
      result = TXmlReader::IsNodeType(this, XmlNodeType_EndElement);
      if ( !(_DWORD)result )
      {
        result = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)this + 112LL))(
                   *(_QWORD *)this,
                   &v14,
                   0);
        if ( !(_DWORD)result )
        {
          v10 = v14 - (_QWORD)a2;
          do
          {
            v11 = *(const unsigned __int16 *)((char *)a2 + v10);
            v12 = *a2 - v11;
            if ( v12 )
              break;
            ++a2;
          }
          while ( v11 );
          if ( v12 )
            return 1;
        }
      }
      return result;
    }
    v15 = XmlNodeType_None;
    result = TXmlReader::Read(this, &v15);
  }
  while ( !(_DWORD)result );
  return result;
}

```

## disassembly

```asm
0x180010d18  mov     rax, rsp
0x180010d1b  mov     [rax+8], rbx
0x180010d1f  mov     [rax+10h], rsi
0x180010d23  push    rdi
0x180010d24  sub     rsp, 30h
0x180010d28  mov     rsi, r8
0x180010d2b  mov     qword ptr [rax-10h], 0
0x180010d33  mov     rbx, rdx
0x180010d36  mov     qword ptr [rax-18h], 0
0x180010d3e  mov     rdi, rcx
0x180010d41  mov     rcx, [rdi]
0x180010d44  lea     rdx, [rsp+38h+var_18]
0x180010d49  xor     r8d, r8d
0x180010d4c  mov     rax, [rcx]
0x180010d4f  mov     rax, [rax+68h]
0x180010d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d58  test    eax, eax
0x180010d5a  jnz     loc_180010DEF
0x180010d60  mov     rcx, [rsp+38h+var_18]
0x180010d65  mov     rax, rsi
0x180010d68  sub     rcx, rsi
0x180010d6b  movzx   edx, word ptr [rax]
0x180010d6e  movzx   r8d, word ptr [rax+rcx]
0x180010d73  sub     edx, r8d
0x180010d76  jnz     short loc_180010D81
0x180010d78  add     rax, 2
0x180010d7c  test    r8d, r8d
0x180010d7f  jnz     short loc_180010D6B
0x180010d81  mov     rcx, rdi; this
0x180010d84  test    edx, edx
0x180010d86  jz      short loc_180010DA0
0x180010d88  lea     rdx, [rsp+38h+arg_18]; enum XmlNodeType *
0x180010d8d  mov     [rsp+38h+arg_18], 0
0x180010d95  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010d9a  test    eax, eax
0x180010d9c  jz      short loc_180010D41
0x180010d9e  jmp     short loc_180010DEF
0x180010da0  mov     edx, 0Fh; enum XmlNodeType
0x180010da5  call    ?IsNodeType@TXmlReader@@QEAAJW4XmlNodeType@@@Z; TXmlReader::IsNodeType(XmlNodeType)
0x180010daa  test    eax, eax
0x180010dac  jnz     short loc_180010DEF
0x180010dae  mov     rcx, [rdi]
0x180010db1  lea     rdx, [rsp+38h+var_10]
0x180010db6  xor     r8d, r8d
0x180010db9  mov     rax, [rcx]
0x180010dbc  mov     rax, [rax+70h]
0x180010dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dc5  test    eax, eax
0x180010dc7  jnz     short loc_180010DEF
0x180010dc9  mov     r8, [rsp+38h+var_10]
0x180010dce  sub     r8, rbx
0x180010dd1  movzx   edx, word ptr [rbx]
0x180010dd4  movzx   ecx, word ptr [rbx+r8]
0x180010dd9  sub     edx, ecx
0x180010ddb  jnz     short loc_180010DE5
0x180010ddd  add     rbx, 2
0x180010de1  test    ecx, ecx
0x180010de3  jnz     short loc_180010DD1
0x180010de5  test    edx, edx
0x180010de7  mov     ecx, 1
0x180010dec  cmovnz  eax, ecx
0x180010def  mov     rbx, [rsp+38h+arg_0]
0x180010df4  mov     rsi, [rsp+38h+arg_8]
0x180010df9  add     rsp, 30h
0x180010dfd  pop     rdi
0x180010dfe  retn
```
