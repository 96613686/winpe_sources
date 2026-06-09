# wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)

- ea: `0x140002338`
- end: `0x1400023ac`
- name: `??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005e44`

## callees

- `0x1400021bc`
- `0x140003390`
- `0x140009d00`

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
0x140002338  mov     r11, rsp
0x14000233b  mov     [r11+8], rcx
0x14000233f  push    rbx
0x140002340  sub     rsp, 0A0h
0x140002347  mov     rax, cs:__security_cookie
0x14000234e  xor     rax, rsp
0x140002351  mov     [rsp+0A8h+var_10], rax
0x140002359  mov     rax, rdx
0x14000235c  lea     rcx, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140002363  mov     [r11-80h], rcx
0x140002367  lea     rdx, [rsp+0A8h+var_88]
0x14000236c  lea     rcx, [r11+8]
0x140002370  mov     [r11-78h], rcx
0x140002374  lea     rcx, [r11-80h]
0x140002378  mov     [r11-18h], rcx
0x14000237c  mov     rcx, rax
0x14000237f  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x140002384  lea     rcx, [rsp+0A8h+var_88]
0x140002389  mov     ebx, eax
0x14000238b  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x140002390  mov     eax, ebx
0x140002392  mov     rcx, [rsp+0A8h+var_10]
0x14000239a  xor     rcx, rsp; StackCookie
0x14000239d  call    __security_check_cookie
0x1400023a2  add     rsp, 0A0h
0x1400023a9  pop     rbx
0x1400023aa  retn
```
