# TelemetryLogger::FireEvent_(void)

- ea: `0x180014f00`
- end: `0x180014f8d`
- name: `?FireEvent_@TelemetryLogger@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(TelemetryLogger *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180014880`
- `0x1800148b0`
- `0x180014980`
- `0x180014f90`

## callees

- `0x180014b30`
- `0x180014f00`
- `0x18004c070`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180014f74`
- `KERNEL32!SetThreadpoolTimer` at `0x180014f74`

## pseudocode

```c
void __fastcall TelemetryLogger::FireEvent_(TelemetryLogger *this)
{
  unsigned int v2; // ecx
  __int64 v3; // rax
  struct _TP_TIMER *v4; // rcx
  _QWORD v5[8]; // [rsp+20h] [rbp-58h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-18h] BYREF

  v5[0] = ___7___Func_impl_no_alloc_V_lambda_1___1__FireEvent__TelemetryLogger__QEAAXXZ_XPEB_WPEB_WJ_std__6B_;
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
0x180014f00  push    rbx
0x180014f02  sub     rsp, 70h
0x180014f06  mov     rax, cs:__security_cookie
0x180014f0d  xor     rax, rsp
0x180014f10  mov     [rsp+78h+var_10], rax
0x180014f15  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??FireEvent_@TelemetryLogger@@QEAAXXZ@XPEB_WPEB_WJ@std@@6B@; const std::_Func_impl_no_alloc<`TelemetryLogger::FireEvent_(void)'::`2'::_lambda_1_,void,wchar_t const *,wchar_t const *,long>::`vftable'
0x180014f1c  mov     rbx, rcx
0x180014f1f  mov     [rsp+78h+var_58], rax
0x180014f24  lea     rdx, [rsp+78h+var_58]
0x180014f29  lea     rax, [rsp+78h+var_58]
0x180014f2e  add     rcx, 20h ; ' '
0x180014f32  mov     [rsp+78h+var_20], rax
0x180014f37  call    ?Flush@ApiDataList@TelemetryLogger@@QEAAXV?$function@$$A6AXPEB_W0J@Z@std@@@Z; TelemetryLogger::ApiDataList::Flush(std::function<void (wchar_t const *,wchar_t const *,long)>)
0x180014f3c  mov     ecx, [rbx+4Ch]
0x180014f3f  mov     eax, [rbx+48h]
0x180014f42  cmp     eax, ecx
0x180014f44  jnb     short loc_180014F54
0x180014f46  add     eax, eax
0x180014f48  mov     [rbx+48h], eax
0x180014f4b  cmp     eax, ecx
0x180014f4d  jbe     short loc_180014F54
0x180014f4f  mov     [rbx+48h], ecx
0x180014f52  mov     eax, ecx
0x180014f54  mov     rcx, [rbx+40h]; pti
0x180014f58  test    rcx, rcx
0x180014f5b  jz      short loc_180014F7A
0x180014f5d  imul    rdx, rax, 0FFFFFFFFFF676980h
0x180014f64  xor     r9d, r9d; msWindowLength
0x180014f67  xor     r8d, r8d; msPeriod
0x180014f6a  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], rdx
0x180014f6f  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180014f74  call    cs:__imp_SetThreadpoolTimer
0x180014f7a  mov     rcx, [rsp+78h+var_10]
0x180014f7f  xor     rcx, rsp; StackCookie
0x180014f82  call    __security_check_cookie
0x180014f87  add     rsp, 70h
0x180014f8b  pop     rbx
0x180014f8c  retn
```
