# Windows::COM::CEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer(unsigned __int64,uchar * const,unsigned __int64 *)

- ea: `0x18007ae90`
- end: `0x18007afda`
- name: `?CurrentIntoBuffer@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@MEAAJ_KQEAEPEA_K@Z`
- size: `330`
- prototype: `int(Windows::COM::CEnumIDENTITY_ATTRIBUTE *__hidden this, unsigned __int64, unsigned __int8 *const, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x180079914`
- `0x18007ae90`
- `0x180097e20`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18007afb1`
- `ntdll!RtlRaiseStatus` at `0x18007afb1`

## string_xrefs

- `0x18007aee3`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007af28`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007aefa`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`
- `0x18007af3f`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`

## pseudocode

```c
__int64 __fastcall Windows::COM::CEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer(
        Windows::COM::CEnumIDENTITY_ATTRIBUTE *this,
        const struct Windows::Identity::Rtl::_ATTRIBUTE *a2,
        unsigned __int8 *const a3,
        unsigned __int64 *a4)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  unsigned __int64 *v10; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 *v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h]
  const char *v13; // [rsp+38h] [rbp-20h]
  int v14; // [rsp+40h] [rbp-18h] BYREF

  v4 = 0;
  v14 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && a3 )
    memset(a3, 0, (size_t)a2);
  if ( !a4 )
  {
    v12 = 178;
    v10 = (unsigned __int64 *)"onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v11 = (unsigned __int64 *)"Windows::COM::CEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer";
    v13 = "Not-null check failed: pcbDataOut";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v10);
  }
  if ( a2 && !a3 )
  {
    v12 = 179;
    v10 = (unsigned __int64 *)"onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v11 = (unsigned __int64 *)"Windows::COM::CEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer";
    v13 = "(cbData == 0) || (pvDataOut != 0)";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v14,
             &v10,
             a3);
  }
  if ( *((_QWORD *)this + 2) )
  {
    v10 = (unsigned __int64 *)(*((_QWORD *)this + 1) + 72LL * *((_QWORD *)this + 3));
    v11 = v10 + 3;
    v12 = (__int64)(v10 + 6);
    result = Windows::COM::CopyOut((Windows::COM *)&v10, a2, (unsigned __int64)a3, a4, v10);
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    v4 = 1;
  }
  if ( *a4 > (unsigned __int64)a2 )
    RtlRaiseStatus(-1073741595);
  return v4;
}

```

## disassembly

```asm
0x18007ae90  push    rbp
0x18007ae92  push    rbx
0x18007ae93  push    rsi
0x18007ae94  push    rdi
0x18007ae95  push    r14
0x18007ae97  push    r15
0x18007ae99  mov     rbp, rsp
0x18007ae9c  sub     rsp, 58h
0x18007aea0  mov     rax, cs:__security_cookie
0x18007aea7  xor     rax, rsp
0x18007aeaa  mov     [rbp+var_10], rax
0x18007aeae  xor     ebx, ebx
0x18007aeb0  mov     rsi, r9
0x18007aeb3  mov     [rbp+var_18], ebx
0x18007aeb6  mov     r14, r8
0x18007aeb9  mov     rdi, rdx
0x18007aebc  mov     r15, rcx
0x18007aebf  test    r9, r9
0x18007aec2  jz      short loc_18007AEC7
0x18007aec4  mov     [r9], rbx
0x18007aec7  test    rdi, rdi
0x18007aeca  jz      short loc_18007AEDE
0x18007aecc  test    r14, r14
0x18007aecf  jz      short loc_18007AEDE
0x18007aed1  mov     r8, rdi; Size
0x18007aed4  xor     edx, edx; Val
0x18007aed6  mov     rcx, r14; void *
0x18007aed9  call    memset
0x18007aede  test    rsi, rsi
0x18007aee1  jnz     short loc_18007AF1E
0x18007aee3  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007aeea  mov     [rbp+var_28], 0B2h
0x18007aef2  mov     [rbp+var_38], rax
0x18007aef6  lea     rdx, [rbp+var_38]
0x18007aefa  lea     rax, aWindowsComCenu_4; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007af01  mov     [rbp+var_30], rax
0x18007af05  lea     rcx, [rbp+var_18]
0x18007af09  lea     rax, aNotNullCheckFa_87; "Not-null check failed: pcbDataOut"
0x18007af10  mov     [rbp+var_20], rax
0x18007af14  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007af19  jmp     loc_18007AFC0
0x18007af1e  test    rdi, rdi
0x18007af21  jz      short loc_18007AF60
0x18007af23  test    r14, r14
0x18007af26  jnz     short loc_18007AF60
0x18007af28  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007af2f  mov     [rbp+var_28], 0B3h
0x18007af37  mov     [rbp+var_38], rax
0x18007af3b  lea     rdx, [rbp+var_38]
0x18007af3f  lea     rax, aWindowsComCenu_4; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007af46  mov     [rbp+var_30], rax
0x18007af4a  lea     rcx, [rbp+var_18]
0x18007af4e  lea     rax, aCbdata0Pvdatao; "(cbData == 0) || (pvDataOut != 0)"
0x18007af55  mov     [rbp+var_20], rax
0x18007af59  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007af5e  jmp     short loc_18007AFC0
0x18007af60  cmp     [r15+10h], rbx
0x18007af64  jz      short loc_18007AFA2
0x18007af66  mov     rax, [r15+18h]
0x18007af6a  mov     r9, rsi; void *
0x18007af6d  mov     r8, r14; unsigned __int64
0x18007af70  lea     rcx, [rax+rax*8]
0x18007af74  mov     rax, [r15+8]
0x18007af78  lea     rdx, [rax+rcx*8]
0x18007af7c  lea     rax, [rdx+18h]
0x18007af80  mov     [rbp+var_38], rdx
0x18007af84  mov     [rbp+var_30], rax
0x18007af88  lea     rcx, [rbp+var_38]; this
0x18007af8c  lea     rax, [rdx+30h]
0x18007af90  mov     rdx, rdi; struct Windows::Identity::Rtl::_ATTRIBUTE *
0x18007af93  mov     [rbp+var_28], rax
0x18007af97  call    ?CopyOut@COM@Windows@@YAJAEBU_ATTRIBUTE@Rtl@Identity@2@_KPEAXPEA_K@Z; Windows::COM::CopyOut(Windows::Identity::Rtl::_ATTRIBUTE const &,unsigned __int64,void *,unsigned __int64 *)
0x18007af9c  test    eax, eax
0x18007af9e  jns     short loc_18007AFA7
0x18007afa0  jmp     short loc_18007AFC0
0x18007afa2  mov     ebx, 1
0x18007afa7  cmp     [rsi], rdi
0x18007afaa  jbe     short loc_18007AFBE
0x18007afac  mov     ecx, 0C00000E5h; Status
0x18007afb1  call    cs:__imp_RtlRaiseStatus
0x18007afb8  nop     dword ptr [rax+rax+00h]
0x18007afbd  int     3; Trap to Debugger
0x18007afbe  mov     eax, ebx
0x18007afc0  mov     rcx, [rbp+var_10]
0x18007afc4  xor     rcx, rsp; StackCookie
0x18007afc7  call    __security_check_cookie
0x18007afcc  add     rsp, 58h
0x18007afd0  pop     r15
0x18007afd2  pop     r14
0x18007afd4  pop     rdi
0x18007afd5  pop     rsi
0x18007afd6  pop     rbx
0x18007afd7  pop     rbp
0x18007afd8  retn
```
