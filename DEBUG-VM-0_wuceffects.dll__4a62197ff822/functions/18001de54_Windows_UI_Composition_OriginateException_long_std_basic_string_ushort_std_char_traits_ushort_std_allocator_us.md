# Windows::UI::Composition::OriginateException(long,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001de54`
- end: `0x18001deb7`
- name: `?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `99`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `28`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001c84`
- `0x180001ce4`
- `0x1800024f0`
- `0x180002858`
- `0x180002dec`
- `0x18000303c`
- `0x1800032f4`
- `0x180003ad0`
- `0x18000448c`
- `0x180004550`
- `0x1800050d0`
- `0x180005440`
- `0x180005ce0`
- `0x180006e1c`
- `0x180007d80`
- `0x180008b90`
- `0x180009730`
- `0x180009b3c`
- `0x18000c9b8`
- `0x1800160c4`
- `0x1800180c0`
- `0x180019e40`
- `0x18001a9c0`
- `0x18001aef0`
- `0x18001bff0`
- `0x180025b50`
- `0x18002699c`
- `0x180027f30`

## callees

- `0x18001c314`
- `0x18001de54`
- `0x18001dec0`
- `0x18002b8b0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001de77`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001de77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn Windows::UI::Composition::OriginateException(__int64 a1, __int64 *a2)
{
  __int64 *v3; // r8
  int v4; // edx
  _QWORD pExceptionObject[26]; // [rsp+20h] [rbp-F8h] BYREF
  _BYTE v6[40]; // [rsp+F0h] [rbp-28h] BYREF

  if ( (unsigned __int64)a2[3] <= 7 )
    v3 = a2;
  else
    v3 = (__int64 *)*a2;
  RoOriginateErrorW(2147942487LL, *((unsigned int *)a2 + 4), v3);
  wil::ResultException::ResultException((wil::ResultException *)pExceptionObject, v4);
  pExceptionObject[0] = &Windows::UI::Composition::OriginatedException::`vftable';
  std::wstring::wstring(v6, a2);
  throw (Windows::UI::Composition::OriginatedException *)pExceptionObject;
}

```

## disassembly

```asm
0x18001de54  push    rbx
0x18001de56  sub     rsp, 110h
0x18001de5d  mov     rbx, rdx
0x18001de60  cmp     qword ptr [rdx+18h], 7
0x18001de65  jbe     short loc_18001DE6C
0x18001de67  mov     r8, [rdx]
0x18001de6a  jmp     short loc_18001DE6F
0x18001de6c  mov     r8, rbx
0x18001de6f  mov     edx, [rdx+10h]
0x18001de72  mov     ecx, 80070057h
0x18001de77  call    cs:__imp_RoOriginateErrorW
0x18001de7d  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18001de82  call    ??0ResultException@wil@@QEAA@J@Z; wil::ResultException::ResultException(long)
0x18001de87  nop
0x18001de88  lea     rax, ??_7OriginatedException@Composition@UI@Windows@@6B@; const Windows::UI::Composition::OriginatedException::`vftable'
0x18001de8f  mov     [rsp+118h+pExceptionObject], rax
0x18001de94  mov     rdx, rbx
0x18001de97  lea     rcx, [rsp+118h+var_28]
0x18001de9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dea4  nop
0x18001dea5  lea     rdx, _TI3?AVOriginatedException@Composition@UI@Windows@@; pThrowInfo
0x18001deac  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18001deb1  call    _CxxThrowException_0
```
