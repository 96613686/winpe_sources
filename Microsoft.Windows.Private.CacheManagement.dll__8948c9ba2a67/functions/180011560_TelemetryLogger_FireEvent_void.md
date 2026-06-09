# TelemetryLogger::FireEvent_(void)

- ea: `0x180011560`
- end: `0x1800115ed`
- name: `?FireEvent_@TelemetryLogger@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(TelemetryLogger *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180010ee0`
- `0x180010f10`
- `0x180010fe0`
- `0x1800115f0`

## callees

- `0x180011190`
- `0x180011560`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1800115d4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800115d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TelemetryLogger::FireEvent_(TelemetryLogger *this)
{
  unsigned int v2; // ecx
  __int64 v3; // rax
  struct _TP_TIMER *v4; // rcx
  _QWORD v5[8]; // [rsp+20h] [rbp-58h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-18h] BYREF

  v5[0] = &std::_Func_impl_no_alloc<_lambda_758cc192c2b6814ec8090745d2a6079d_,void,wchar_t const *,wchar_t const *,long>::`vftable';
  v5[7] = v5;
  TelemetryLogger::ApiDataList::Flush((char *)this + 32, v5);
  v2 = *((_DWORD *)this + 19);
  v3 = *((unsigned int *)this + 18);
  if ( (unsigned int)v3 < v2 )
  {
    v3 = (unsigned int)(2 * v3);
    *((_DWORD *)this + 18) = v3;
    if ( (unsigned int)v3 > v2 )
    {
      *((_DWORD *)this + 18) = v2;
      v3 = v2;
    }
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v4 )
  {
    pftDueTime = (struct _FILETIME)(-10000000 * v3);
    SetThreadpoolTimer(v4, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x180011560  push    rbx
0x180011562  sub     rsp, 70h
0x180011566  mov     rax, cs:__security_cookie
0x18001156d  xor     rax, rsp
0x180011570  mov     [rsp+78h+var_10], rax
0x180011575  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_758cc192c2b6814ec8090745d2a6079d_@@XPEB_WPEB_WJ@std@@6B@; const std::_Func_impl_no_alloc<_lambda_758cc192c2b6814ec8090745d2a6079d_,void,wchar_t const *,wchar_t const *,long>::`vftable'
0x18001157c  mov     rbx, rcx
0x18001157f  mov     [rsp+78h+var_58], rax
0x180011584  lea     rdx, [rsp+78h+var_58]
0x180011589  lea     rax, [rsp+78h+var_58]
0x18001158e  add     rcx, 20h ; ' '
0x180011592  mov     [rsp+78h+var_20], rax
0x180011597  call    ?Flush@ApiDataList@TelemetryLogger@@QEAAXV?$function@$$A6AXPEB_W0J@Z@std@@@Z; TelemetryLogger::ApiDataList::Flush(std::function<void (wchar_t const *,wchar_t const *,long)>)
0x18001159c  mov     ecx, [rbx+4Ch]
0x18001159f  mov     eax, [rbx+48h]
0x1800115a2  cmp     eax, ecx
0x1800115a4  jnb     short loc_1800115B4
0x1800115a6  add     eax, eax
0x1800115a8  mov     [rbx+48h], eax
0x1800115ab  cmp     eax, ecx
0x1800115ad  jbe     short loc_1800115B4
0x1800115af  mov     [rbx+48h], ecx
0x1800115b2  mov     eax, ecx
0x1800115b4  mov     rcx, [rbx+40h]; pti
0x1800115b8  test    rcx, rcx
0x1800115bb  jz      short loc_1800115DA
0x1800115bd  imul    rdx, rax, 0FFFFFFFFFF676980h
0x1800115c4  xor     r9d, r9d; msWindowLength
0x1800115c7  xor     r8d, r8d; msPeriod
0x1800115ca  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], rdx
0x1800115cf  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800115d4  call    cs:__imp_SetThreadpoolTimer
0x1800115da  mov     rcx, [rsp+78h+var_10]
0x1800115df  xor     rcx, rsp; StackCookie
0x1800115e2  call    __security_check_cookie
0x1800115e7  add     rsp, 70h
0x1800115eb  pop     rbx
0x1800115ec  retn
```
