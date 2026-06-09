# CSMBHelperClass::GenerateRepairInfo(ulong)

- ea: `0x1800051b4`
- end: `0x180005312`
- name: `?GenerateRepairInfo@CSMBHelperClass@@AEAAJK@Z`
- size: `350`
- prototype: `__int64 __fastcall(CSMBHelperClass *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800067d0`

## callees

- `0x18000123c`
- `0x1800051b4`
- `0x18000a690`
- `0x18000dd04`
- `0x18000e10c`
- `0x18000f850`
- `0x18000f8e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800052f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800052f9`

## string_xrefs

- `0x180005296`: `SharePath`
- `0x1800052b4`: `ServerPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSMBHelperClass::GenerateRepairInfo(CSMBHelperClass *this, int a2)
{
  unsigned int v3; // esi
  AttributeList *v4; // rbx
  AttributeList *v5; // rcx
  __int64 v6; // rax
  RevokableAccessor *v7; // rax
  RevokableAccessor *v8; // rbx
  char *v9; // rdi
  unsigned __int16 *v10; // r14
  __int64 Attribute; // rax
  _BYTE v13[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v14[24]; // [rsp+38h] [rbp-50h] BYREF
  char v15[56]; // [rsp+50h] [rbp-38h] BYREF
  RevokableAccessor *v16; // [rsp+A0h] [rbp+18h]

  v3 = 0;
  if ( (a2 & 0xFFFFFFF9) != 0 || a2 == 6 )
  {
    if ( a2 == 6 )
    {
      try
      {
        v7 = (RevokableAccessor *)operator new(0x30u);
        v8 = v7;
        if ( v7 )
        {
          RevokableAccessor::RevokableAccessor(v7);
          v9 = (char *)this + 208;
          *((_QWORD *)v8 + 5) = v9;
        }
        else
        {
          v9 = (char *)this + 208;
        }
        v16 = v8;
        v10 = *(unsigned __int16 **)(AttributeList::getAttribute(v9, v13, L"SharePath", 1) + 8);
        Attribute = AttributeList::getAttribute(v9, v15, L"ServerPath", 1);
        ShareConnectTest::GenerateRepairInfo(*(unsigned __int16 **)(Attribute + 8), v10, v8);
      }
      catch ( enum TestException )
      {
        v3 = -2147467259;
        v8 = v16;
      }
      if ( v8 )
      {
        RevokableAccessor::~RevokableAccessor(v8);
        operator delete(v8);
      }
    }
  }
  else
  {
    v4 = (CSMBHelperClass *)((char *)this + 208);
    v5 = (CSMBHelperClass *)((char *)this + 208);
    try
    {
      AttributeList::setStringAttribute(v5, L"Hypothesis", L"NetBt");
      v6 = AttributeList::getAttribute(v4, v13, L"ServerName", 1);
      AttributeList::setStringAttribute(v4, L"NetBt:name", *(unsigned __int16 **)(v6 + 8));
      AttributeList::setStringAttribute(v4, L"NetBt:appid", L"System");
    }
    catch ( exception v14 )
    {
      exception::~exception((exception *)v14);
      return (unsigned int)-2147467259;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800051b4  mov     [rsp+arg_0], rbx
0x1800051b9  push    rsi
0x1800051ba  push    rdi
0x1800051bb  push    r14
0x1800051bd  sub     rsp, 70h
0x1800051c1  mov     rdi, rcx
0x1800051c4  xor     esi, esi
0x1800051c6  test    edx, 0FFFFFFF9h
0x1800051cc  jnz     short loc_180005243
0x1800051ce  cmp     edx, 6
0x1800051d1  jz      short loc_180005243
0x1800051d3  lea     rbx, [rcx+0D0h]
0x1800051da  lea     r8, aNetbt; "NetBt"
0x1800051e1  lea     rdx, aHypothesis; "Hypothesis"
0x1800051e8  mov     rcx, rbx; this
0x1800051eb  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x1800051f0  lea     r9d, [rsi+1]
0x1800051f4  lea     r8, aServername; "ServerName"
0x1800051fb  lea     rdx, [rsp+88h+var_68]
0x180005200  mov     rcx, rbx
0x180005203  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180005208  mov     r8, [rax+8]; unsigned __int16 *
0x18000520c  lea     rdx, aNetbtName; "NetBt:name"
0x180005213  mov     rcx, rbx; this
0x180005216  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x18000521b  lea     r8, aSystem_0; "System"
0x180005222  lea     rdx, aNetbtAppid; "NetBt:appid"
0x180005229  mov     rcx, rbx; this
0x18000522c  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005231  nop
0x180005232  jmp     loc_1800052FF
0x180005237  mov     esi, [rsp+88h+arg_8]
0x18000523e  jmp     loc_1800052FF
0x180005243  mov     [rsp+88h+arg_10], rsi
0x18000524b  cmp     edx, 6
0x18000524e  jnz     loc_1800052FF
0x180005254  lea     ecx, [rdx+2Ah]; Size
0x180005257  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000525c  mov     rbx, rax
0x18000525f  mov     [rsp+88h+arg_18], rax
0x180005267  test    rbx, rbx
0x18000526a  jz      short loc_180005281
0x18000526c  mov     rcx, rax; this
0x18000526f  call    ??0RevokableAccessor@@QEAA@XZ; RevokableAccessor::RevokableAccessor(void)
0x180005274  add     rdi, 0D0h
0x18000527b  mov     [rbx+28h], rdi
0x18000527f  jmp     short loc_180005288
0x180005281  add     rdi, 0D0h
0x180005288  mov     [rsp+88h+arg_10], rbx
0x180005290  mov     r9d, 1
0x180005296  lea     r8, aSharepath; "SharePath"
0x18000529d  lea     rdx, [rsp+88h+var_68]
0x1800052a2  mov     rcx, rdi
0x1800052a5  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x1800052aa  mov     r14, [rax+8]
0x1800052ae  mov     r9d, 1
0x1800052b4  lea     r8, aServerpath; "ServerPath"
0x1800052bb  lea     rdx, [rsp+88h+var_38]
0x1800052c0  mov     rcx, rdi
0x1800052c3  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x1800052c8  mov     r8, rbx; struct AttributeListAccessor *
0x1800052cb  mov     rdx, r14; unsigned __int16 *
0x1800052ce  mov     rcx, [rax+8]; unsigned __int16 *
0x1800052d2  call    ?GenerateRepairInfo@ShareConnectTest@@SAXPEAG0PEAVAttributeListAccessor@@@Z; ShareConnectTest::GenerateRepairInfo(ushort *,ushort *,AttributeListAccessor *)
0x1800052d7  nop
0x1800052d8  jmp     short loc_1800052E9
0x1800052da  mov     esi, [rsp+88h+arg_8]
0x1800052e1  mov     rbx, [rsp+88h+arg_10]
0x1800052e9  test    rbx, rbx
0x1800052ec  jz      short loc_1800052FF
0x1800052ee  mov     rcx, rbx; this
0x1800052f1  call    ??1RevokableAccessor@@QEAA@XZ; RevokableAccessor::~RevokableAccessor(void)
0x1800052f6  mov     rcx, rbx
0x1800052f9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800052ff  mov     eax, esi
0x180005301  mov     rbx, [rsp+88h+arg_0]
0x180005309  add     rsp, 70h
0x18000530d  pop     r14
0x18000530f  pop     rdi
0x180005310  pop     rsi
0x180005311  retn
```
