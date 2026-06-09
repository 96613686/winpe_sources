# wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)

- ea: `0x1400022e4`
- end: `0x140002357`
- name: `??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005b1c`

## callees

- `0x140002168`
- `0x14000334c`
- `0x1400096d0`

## pseudocode

```c
__int64 __fastcall wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  unsigned int v2; // ebx
  _BYTE v4[8]; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v5[14]; // [rsp+28h] [rbp-80h] BYREF
  __int64 v6; // [rsp+B0h] [rbp+8h] BYREF

  v6 = a1;
  v5[0] = &wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v5[1] = &v6;
  v5[13] = v5;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         a2,
         (__int64)v4);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v4);
  return v2;
}

```

## disassembly

```asm
0x1400022e4  mov     r11, rsp
0x1400022e7  mov     [r11+8], rcx
0x1400022eb  push    rbx
0x1400022ec  sub     rsp, 0A0h
0x1400022f3  mov     rax, cs:__security_cookie
0x1400022fa  xor     rax, rsp
0x1400022fd  mov     [rsp+0A8h+var_10], rax
0x140002305  mov     rax, rdx
0x140002308  lea     rcx, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x14000230f  mov     [r11-80h], rcx
0x140002313  lea     rdx, [rsp+0A8h+var_88]
0x140002318  lea     rcx, [r11+8]
0x14000231c  mov     [r11-78h], rcx
0x140002320  lea     rcx, [r11-80h]
0x140002324  mov     [r11-18h], rcx
0x140002328  mov     rcx, rax
0x14000232b  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x140002330  lea     rcx, [rsp+0A8h+var_88]
0x140002335  mov     ebx, eax
0x140002337  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x14000233c  mov     eax, ebx
0x14000233e  mov     rcx, [rsp+0A8h+var_10]
0x140002346  xor     rcx, rsp; StackCookie
0x140002349  call    __security_check_cookie
0x14000234e  add     rsp, 0A0h
0x140002355  pop     rbx
0x140002356  retn
```
