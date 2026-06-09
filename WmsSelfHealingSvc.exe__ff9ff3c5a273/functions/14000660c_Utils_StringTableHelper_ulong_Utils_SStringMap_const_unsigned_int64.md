# Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)

- ea: `0x14000660c`
- end: `0x1400066eb`
- name: `?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z`
- size: `223`
- prototype: `const unsigned __int16 *__fastcall(Utils *this, __int64, const struct Utils::SStringMap *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006544`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x14000660c`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140006672`
- `KERNEL32!IsDebuggerPresent` at `0x140006672`

## string_xrefs

- `0x140006661`: `termsrv\wms\src\common\srcutils\debughelpers.cpp`
- `0x140006693`: `termsrv\wms\src\common\srcutils\debughelpers.cpp`
- `0x1400066b6`: `termsrv\wms\src\common\srcutils\debughelpers.cpp`

## pseudocode

```c
const unsigned __int16 *__fastcall Utils::StringTableHelper(
        Utils *this,
        __int64 a2,
        const struct Utils::SStringMap *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rax
  __int64 v5; // rbx

  v4 = 0;
  while ( LODWORD(qword_14000D110[2 * v4]) != (_DWORD)this )
  {
    if ( (unsigned __int64)++v4 >= 5 )
    {
      v5 = 0;
      goto LABEL_6;
    }
  }
  v5 = qword_14000D110[2 * v4 + 1];
  if ( v5 )
    return (const unsigned __int16 *)v5;
LABEL_6:
  LOGASSERT(L"termsrv\\wms\\src\\common\\srcutils\\debughelpers.cpp", 32, L"Utils::StringTableHelper", a4, L"psz");
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
      L"termsrv\\wms\\src\\common\\srcutils\\debughelpers.cpp");
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
      L"termsrv\\wms\\src\\common\\srcutils\\debughelpers.cpp",
      32,
      L"Utils::StringTableHelper",
      L"ASSERT",
      L"psz");
  return (const unsigned __int16 *)v5;
}

```

## disassembly

```asm
0x14000660c  mov     [rsp+arg_0], rbx
0x140006611  mov     [rsp+arg_8], rbp
0x140006616  push    r14
0x140006618  sub     rsp, 40h
0x14000661c  xor     eax, eax
0x14000661e  lea     rbx, qword_14000D110
0x140006625  mov     rdx, rax
0x140006628  add     rdx, rdx
0x14000662b  cmp     [rbx+rdx*8], ecx
0x14000662e  jz      short loc_14000663D
0x140006630  inc     rax
0x140006633  cmp     rax, 5
0x140006637  jb      short loc_140006625
0x140006639  xor     ebx, ebx
0x14000663b  jmp     short loc_14000664B
0x14000663d  mov     rbx, [rbx+rdx*8+8]
0x140006642  test    rbx, rbx
0x140006645  jnz     loc_1400066D7
0x14000664b  lea     rbp, aUtilsStringtab; "Utils::StringTableHelper"
0x140006652  mov     edx, 20h ; ' '; unsigned int
0x140006657  lea     r14, aPsz; "psz"
0x14000665e  mov     r8, rbp; unsigned __int16 *
0x140006661  lea     rcx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\de"...
0x140006668  mov     [rsp+48h+var_28], r14; unsigned __int16 *
0x14000666d  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140006672  call    cs:__imp_IsDebuggerPresent
0x140006678  test    eax, eax
0x14000667a  lea     rax, aAssert; "ASSERT"
0x140006681  jz      short loc_1400066B1
0x140006683  mov     r9d, 20h ; ' '
0x140006689  mov     [rsp+48h+var_18], r14
0x14000668e  mov     [rsp+48h+var_20], rax
0x140006693  lea     r8, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\de"...
0x14000669a  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400066a1  mov     [rsp+48h+var_28], rbp
0x1400066a6  lea     ecx, [r9-1Eh]; unsigned __int8
0x1400066aa  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400066af  jmp     short loc_1400066D7
0x1400066b1  mov     [rsp+48h+var_20], r14
0x1400066b6  lea     rdx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\de"...
0x1400066bd  mov     r9, rbp
0x1400066c0  mov     [rsp+48h+var_28], rax
0x1400066c5  mov     r8d, 20h ; ' '
0x1400066cb  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400066d2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400066d7  mov     rbp, [rsp+48h+arg_8]
0x1400066dc  mov     rax, rbx
0x1400066df  mov     rbx, [rsp+48h+arg_0]
0x1400066e4  add     rsp, 40h
0x1400066e8  pop     r14
0x1400066ea  retn
```
