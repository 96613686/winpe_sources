# ListReaderGroups(ulong,CBuffer &)

- ea: `0x18002a8ec`
- end: `0x18002aaf0`
- name: `?ListReaderGroups@@YAXKAEAVCBuffer@@@Z`
- size: `516`
- prototype: `void(unsigned int, struct CBuffer *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026190`
- `0x180028000`

## callees

- `0x180002220`
- `0x180003fc0`
- `0x18000a290`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000bd60`
- `0x18000e3d0`
- `0x180010400`
- `0x180014260`
- `0x18002a8ec`
- `0x18002ef20`

## string_xrefs

- `0x18002a948`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`
- `0x18002a986`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall ListReaderGroups(unsigned int a1, struct CBuffer *a2)
{
  unsigned __int16 *v4; // r14
  unsigned __int16 *v5; // rcx
  const WCHAR *i; // rax
  const unsigned __int16 *v7; // rdi
  unsigned int *v8; // r9
  unsigned int j; // r8d
  ulong pExceptionObject; // [rsp+30h] [rbp-A8h] BYREF
  const int *v11; // [rsp+38h] [rbp-A0h] BYREF
  unsigned __int16 *v12; // [rsp+40h] [rbp-98h]
  __int64 v13; // [rsp+48h] [rbp-90h]
  const int *v14; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int16 *v15; // [rsp+58h] [rbp-80h]
  __int64 v16; // [rsp+60h] [rbp-78h]
  _QWORD v17[4]; // [rsp+68h] [rbp-70h] BYREF
  __int64 v18; // [rsp+88h] [rbp-50h]
  ulong v19; // [rsp+90h] [rbp-48h]
  unsigned __int16 *v20; // [rsp+F0h] [rbp+18h] BYREF
  const WCHAR *v21; // [rsp+F8h] [rbp+20h]

  v14 = &CBuffer::`vftable';
  v15 = 0;
  v16 = 0;
  v17[2] = &CBuffer::`vftable';
  v17[3] = 0;
  v18 = 0;
  v17[0] = 0;
  v19 = 1010;
  v11 = &CBuffer::`vftable';
  v12 = 0;
  v13 = 0;
  ListKnownKeys(a1, (__int64)&v14, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers");
  v4 = (unsigned __int16 *)&WideCharStr;
  v5 = (unsigned __int16 *)&WideCharStr;
  if ( HIDWORD(v16) )
    v5 = v15;
  for ( i = FirstString(v5); ; i = NextString(v7) )
  {
    v7 = i;
    v21 = i;
    if ( !i )
      break;
    FindKey(a1, i, (__int64)v17, (__int64)L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers");
    v20 = 0;
    CRegistry::GetValue((CRegistry *)v17, L"Groups", &v20, v8);
    if ( !v20 )
    {
      v11 = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)&v11);
      CRegistry::~CRegistry((CRegistry *)v17);
      v14 = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)&v14);
      return;
    }
    if ( v19 )
    {
      pExceptionObject = v19;
      throw &pExceptionObject;
    }
    for ( j = (unsigned int)v18 >> 1; !v20[j - 1]; --j )
      ;
    CBuffer::Append((CBuffer *)&v11, (const unsigned __int8 *const)v20, 2 * j);
    CBuffer::Append((CBuffer *)&v11, (const unsigned __int8 *const)&WideCharStr, 2u);
  }
  CBuffer::Append((CBuffer *)&v11, (const unsigned __int8 *const)&WideCharStr, 4u);
  if ( HIDWORD(v13) )
    v4 = v12;
  MStringSort(v4, a2);
  v11 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v11);
  CRegistry::~CRegistry((CRegistry *)v17);
  v14 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v14);
}

```

## disassembly

```asm
0x18002a8ec  mov     rax, rsp
0x18002a8ef  mov     [rax+10h], rdx
0x18002a8f3  mov     [rax+8], ecx
0x18002a8f6  push    rbx
0x18002a8f7  push    rsi
0x18002a8f8  push    rdi
0x18002a8f9  push    r12
0x18002a8fb  push    r14
0x18002a8fd  push    r15
0x18002a8ff  sub     rsp, 0A8h
0x18002a906  mov     r12, rdx
0x18002a909  mov     r15d, ecx
0x18002a90c  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002a913  mov     [rsp+0D8h+var_88], rsi
0x18002a918  xor     ebx, ebx
0x18002a91a  mov     [rax-80h], rbx
0x18002a91e  mov     [rax-78h], rbx
0x18002a922  mov     [rax-60h], rsi
0x18002a926  mov     [rax-58h], rbx
0x18002a92a  mov     [rax-50h], rbx
0x18002a92e  mov     [rax-70h], rbx
0x18002a932  mov     dword ptr [rax-48h], 3F2h
0x18002a939  mov     [rsp+0D8h+var_A0], rsi
0x18002a93e  mov     [rsp+0D8h+var_98], rbx
0x18002a943  mov     [rsp+0D8h+var_90], rbx
0x18002a948  lea     r8, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002a94f  lea     rdx, [rsp+0D8h+var_88]
0x18002a954  call    ListKnownKeys
0x18002a959  lea     r14, WideCharStr
0x18002a960  mov     rcx, r14
0x18002a963  cmp     [rsp+0D8h+var_74], ebx
0x18002a967  cmova   rcx, [rsp+0D8h+var_80]; unsigned __int16 *
0x18002a96d  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18002a972  mov     rdi, rax
0x18002a975  mov     [rsp+0D8h+arg_18], rax
0x18002a97d  test    rax, rax
0x18002a980  jz      loc_18002AA8C
0x18002a986  lea     r9, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002a98d  lea     r8, [rsp+0D8h+var_70]
0x18002a992  mov     rdx, rax
0x18002a995  mov     ecx, r15d
0x18002a998  call    FindKey
0x18002a99d  mov     [rsp+0D8h+arg_10], rbx
0x18002a9a5  lea     r8, [rsp+0D8h+arg_10]; unsigned __int16 **
0x18002a9ad  lea     rdx, aGroups_0; "Groups"
0x18002a9b4  lea     rcx, [rsp+0D8h+var_70]; this
0x18002a9b9  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x18002a9be  mov     rdx, [rsp+0D8h+arg_10]
0x18002a9c6  test    rdx, rdx
0x18002a9c9  jnz     short loc_18002A9FA
0x18002a9cb  mov     [rsp+0D8h+var_A0], rsi
0x18002a9d0  lea     rcx, [rsp+0D8h+var_A0]; this
0x18002a9d5  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002a9da  nop
0x18002a9db  lea     rcx, [rsp+0D8h+var_70]; this
0x18002a9e0  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002a9e5  nop
0x18002a9e6  mov     [rsp+0D8h+var_88], rsi
0x18002a9eb  lea     rcx, [rsp+0D8h+var_88]; this
0x18002a9f0  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002a9f5  jmp     loc_18002AADF
0x18002a9fa  mov     eax, [rsp+0D8h+var_48]
0x18002aa01  test    eax, eax
0x18002aa03  jz      short loc_18002AA1A
0x18002aa05  mov     [rsp+0D8h+pExceptionObject], eax
0x18002aa09  lea     rdx, _TI1K; pThrowInfo
0x18002aa10  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18002aa15  call    _CxxThrowException_0
0x18002aa1a  mov     r8d, dword ptr [rsp+0D8h+var_50]
0x18002aa22  shr     r8d, 1
0x18002aa25  jmp     short loc_18002AA2A
0x18002aa27  dec     r8d
0x18002aa2a  lea     eax, [r8-1]
0x18002aa2e  cmp     bx, [rdx+rax*2]
0x18002aa32  jz      short loc_18002AA27
0x18002aa34  add     r8d, r8d; unsigned int
0x18002aa37  lea     rcx, [rsp+0D8h+var_A0]; this
0x18002aa3c  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002aa41  mov     r8d, 2; unsigned int
0x18002aa47  mov     rdx, r14; unsigned __int8 *
0x18002aa4a  lea     rcx, [rsp+0D8h+var_A0]; this
0x18002aa4f  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002aa54  nop
0x18002aa55  jmp     short loc_18002AA7F
0x18002aa57  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002aa5e  xor     ebx, ebx
0x18002aa60  lea     r14, WideCharStr
0x18002aa67  mov     r12, [rsp+0D8h+arg_8]
0x18002aa6f  mov     r15d, [rsp+0D8h+arg_0]
0x18002aa77  mov     rdi, [rsp+0D8h+arg_18]
0x18002aa7f  mov     rcx, rdi; unsigned __int16 *
0x18002aa82  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002aa87  jmp     loc_18002A972
0x18002aa8c  mov     r8d, 4; unsigned int
0x18002aa92  mov     rdx, r14; unsigned __int8 *
0x18002aa95  lea     rcx, [rsp+0D8h+var_A0]; this
0x18002aa9a  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002aa9f  cmp     dword ptr [rsp+0D8h+var_90+4], ebx
0x18002aaa3  cmova   r14, [rsp+0D8h+var_98]
0x18002aaa9  mov     rdx, r12; struct CBuffer *
0x18002aaac  mov     rcx, r14; unsigned __int16 *
0x18002aaaf  call    ?MStringSort@@YAKPEBGAEAVCBuffer@@@Z; MStringSort(ushort const *,CBuffer &)
0x18002aab4  nop
0x18002aab5  mov     [rsp+0D8h+var_A0], rsi
0x18002aaba  lea     rcx, [rsp+0D8h+var_A0]; this
0x18002aabf  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002aac4  nop
0x18002aac5  lea     rcx, [rsp+0D8h+var_70]; this
0x18002aaca  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002aacf  nop
0x18002aad0  mov     [rsp+0D8h+var_88], rsi
0x18002aad5  lea     rcx, [rsp+0D8h+var_88]; this
0x18002aada  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002aadf  add     rsp, 0A8h
0x18002aae6  pop     r15
0x18002aae8  pop     r14
0x18002aaea  pop     r12
0x18002aaec  pop     rdi
0x18002aaed  pop     rsi
0x18002aaee  pop     rbx
0x18002aaef  retn
```
