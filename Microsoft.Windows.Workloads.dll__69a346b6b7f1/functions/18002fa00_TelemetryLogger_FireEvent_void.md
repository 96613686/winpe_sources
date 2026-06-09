# TelemetryLogger::FireEvent_(void)

- ea: `0x18002fa00`
- end: `0x18002fa8d`
- name: `?FireEvent_@TelemetryLogger@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(TelemetryLogger *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f7b0`
- `0x18002fd20`
- `0x18002fd50`
- `0x18002fd80`

## callees

- `0x18002f8b0`
- `0x18002fa00`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18002fa74`
- `KERNEL32!SetThreadpoolTimer` at `0x18002fa74`

## pseudocode

```c
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
0x18002fa00  push    rbx
0x18002fa02  sub     rsp, 70h
0x18002fa06  mov     rax, cs:__security_cookie
0x18002fa0d  xor     rax, rsp
0x18002fa10  mov     [rsp+78h+var_10], rax
0x18002fa15  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_758cc192c2b6814ec8090745d2a6079d_@@XPEB_WPEB_WJ@std@@6B@; const std::_Func_impl_no_alloc<_lambda_758cc192c2b6814ec8090745d2a6079d_,void,wchar_t const *,wchar_t const *,long>::`vftable'
0x18002fa1c  mov     rbx, rcx
0x18002fa1f  mov     [rsp+78h+var_58], rax
0x18002fa24  lea     rdx, [rsp+78h+var_58]
0x18002fa29  lea     rax, [rsp+78h+var_58]
0x18002fa2e  add     rcx, 20h ; ' '
0x18002fa32  mov     [rsp+78h+var_20], rax
0x18002fa37  call    ?Flush@ApiDataList@TelemetryLogger@@QEAAXV?$function@$$A6AXPEB_W0J@Z@std@@@Z; TelemetryLogger::ApiDataList::Flush(std::function<void (wchar_t const *,wchar_t const *,long)>)
0x18002fa3c  mov     ecx, [rbx+4Ch]
0x18002fa3f  mov     eax, [rbx+48h]
0x18002fa42  cmp     eax, ecx
0x18002fa44  jnb     short loc_18002FA54
0x18002fa46  add     eax, eax
0x18002fa48  mov     [rbx+48h], eax
0x18002fa4b  cmp     eax, ecx
0x18002fa4d  jbe     short loc_18002FA54
0x18002fa4f  mov     [rbx+48h], ecx
0x18002fa52  mov     eax, ecx
0x18002fa54  mov     rcx, [rbx+40h]; pti
0x18002fa58  test    rcx, rcx
0x18002fa5b  jz      short loc_18002FA7A
0x18002fa5d  imul    rdx, rax, 0FFFFFFFFFF676980h
0x18002fa64  xor     r9d, r9d; msWindowLength
0x18002fa67  xor     r8d, r8d; msPeriod
0x18002fa6a  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], rdx
0x18002fa6f  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18002fa74  call    cs:__imp_SetThreadpoolTimer
0x18002fa7a  mov     rcx, [rsp+78h+var_10]
0x18002fa7f  xor     rcx, rsp; StackCookie
0x18002fa82  call    __security_check_cookie
0x18002fa87  add     rsp, 70h
0x18002fa8b  pop     rbx
0x18002fa8c  retn
```
