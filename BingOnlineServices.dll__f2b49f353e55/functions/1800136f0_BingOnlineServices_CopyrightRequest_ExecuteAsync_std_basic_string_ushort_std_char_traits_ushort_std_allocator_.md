# BingOnlineServices::CopyrightRequest::ExecuteAsync(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,BingOnlineServices::BoundingBox const &,uint)

- ea: `0x1800136f0`
- end: `0x18001392e`
- name: `?ExecuteAsync@CopyrightRequest@BingOnlineServices@@QEAA?AV?$task@VCopyrightData@BingOnlineServices@@@pplx@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUBoundingBox@2@I@Z`
- size: `574`
- prototype: `__int64 __usercall@<rax>(BingOnlineServices::CopyrightRequest *this@<rcx>, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002c2c`
- `0x180002c6c`
- `0x180004fa0`
- `0x180005e9c`
- `0x180009778`
- `0x18000a2f4`
- `0x18000ab60`
- `0x180011634`
- `0x180011fc4`
- `0x1800136f0`
- `0x180013c90`
- `0x1800148ac`
- `0x18001bd40`
- `0x18001be70`
- `0x18001bfb0`

## import_xrefs

- `ZTrace_Maps!ZTraceHelper` at `0x180013756`
- `ZTrace_Maps!ZTraceHelper` at `0x18001382f`
- `ZTrace_Maps!ZTraceHelper` at `0x1800138d7`
- `ZTrace_Maps!ZTraceHelper` at `0x180013756`
- `ZTrace_Maps!ZTraceHelper` at `0x18001382f`
- `ZTrace_Maps!ZTraceHelper` at `0x1800138d7`

## string_xrefs

- `0x18001374d`: `BingOnlineServices::CopyrightRequest::ExecuteAsync`
- `0x180013826`: `BingOnlineServices::CopyrightRequest::ExecuteAsync`
- `0x1800138cc`: `BingOnlineServices::CopyrightRequest::ExecuteAsync`
- `0x18001375c`: `The query string for a copyright request must not be empty.`
- `0x180013835`: `The bounding box for a copyright request must be valid.`
- `0x1800138b7`: `Executing copyright request`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BingOnlineServices::CopyrightRequest::ExecuteAsync(
        BingOnlineServices::CopyrightRequest *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  _OWORD *v9; // r9
  __int64 v10; // r8
  const WCHAR *ValueFromConfig; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 JsonRequestAsync; // rax
  __int64 pExceptionObject; // [rsp+48h] [rbp-69h] BYREF
  std::_Ref_count_base *v19; // [rsp+50h] [rbp-61h]
  _BYTE v20[40]; // [rsp+68h] [rbp-49h] BYREF
  _OWORD v21[3]; // [rsp+90h] [rbp-21h] BYREF

  pExceptionObject = a2;
  std::wstring::wstring(v20);
  if ( !*(_QWORD *)(v10 + 16) )
  {
    ZTraceHelper(
      0,
      "BingOnlineServices::CopyrightRequest::ExecuteAsync",
      31,
      this,
      "Failed to specify non-empty imagery set");
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)&pExceptionObject,
      "The query string for a copyright request must not be empty.");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  if ( *((_BYTE *)this + 64) )
  {
    ValueFromConfig = BingOnlineServices::CopyrightRequest::GetValueFromConfig(
                        this,
                        (const WCHAR *)&pExceptionObject,
                        0xE2u);
    std::wstring::operator=(v20, ValueFromConfig);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    v12 = std::wstring::wstring(v21);
    v13 = BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(
            (unsigned int)&pExceptionObject,
            (unsigned int)v20,
            (int)this + 32,
            (_DWORD)this,
            v12);
    std::wstring::operator=(v20, v13);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
  }
  else
  {
    v21[0] = *v9;
    v21[1] = v9[1];
    v21[2] = v9[2];
    if ( !(unsigned __int8)BingOnlineServices::BoundingBox::IsValid(v21) )
    {
      ZTraceHelper(
        0,
        "BingOnlineServices::CopyrightRequest::ExecuteAsync",
        44,
        this,
        "Failed to specify valid bounding box");
      std::invalid_argument::invalid_argument(
        (std::invalid_argument *)&pExceptionObject,
        "The bounding box for a copyright request must be valid.");
      throw (std::invalid_argument *)&pExceptionObject;
    }
    v14 = BingOnlineServices::CopyrightRequest::GetValueFromConfig(this, (const WCHAR *)v21, 0xE1u);
    std::wstring::operator=(v20, v14);
    std::wstring::_Tidy_deallocate(v21);
    v15 = BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(
            (unsigned int)v21,
            (unsigned int)v20,
            (int)this + 32,
            (_DWORD)this,
            a3,
            a4,
            a5);
    std::wstring::operator=(v20, v15);
  }
  std::wstring::_Tidy_deallocate(v21);
  ZTraceHelper(5, "BingOnlineServices::CopyrightRequest::ExecuteAsync", 51, this, "Executing copyright request");
  JsonRequestAsync = BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync(&pExceptionObject, v20);
  pplx::task_BingOnlineServices::OnlineServiceResponse_::then__lambda_5d9e762188e201a51595a856687dbe89___(
    JsonRequestAsync,
    a2);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  std::wstring::_Tidy_deallocate(v20);
  return a2;
}

```

## disassembly

```asm
0x1800136f0  push    rbp
0x1800136f2  push    rbx
0x1800136f3  push    rsi
0x1800136f4  push    rdi
0x1800136f5  push    r14
0x1800136f7  push    r15
0x1800136f9  lea     rbp, [rsp-27h]
0x1800136fe  sub     rsp, 0D8h
0x180013705  mov     rax, cs:__security_cookie
0x18001370c  xor     rax, rsp
0x18001370f  mov     [rbp+4Fh+var_40], rax
0x180013713  mov     rsi, r9
0x180013716  mov     r14, r8
0x180013719  mov     rdi, rdx
0x18001371c  mov     rbx, rcx
0x18001371f  mov     [rbp+4Fh+pExceptionObject], rdx
0x180013723  mov     r15d, [rbp+4Fh+arg_20]
0x180013727  lea     rcx, [rbp+4Fh+var_98]
0x18001372b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013730  nop
0x180013731  cmp     qword ptr [r8+10h], 0
0x180013736  jnz     short loc_18001377D
0x180013738  lea     rax, aFailedToSpecif_1; "Failed to specify non-empty imagery set"
0x18001373f  mov     [rsp+100h+var_E0], rax
0x180013744  mov     r9, rbx
0x180013747  mov     r8d, 1Fh
0x18001374d  lea     rdx, aBingonlineserv_0; "BingOnlineServices::CopyrightRequest::E"...
0x180013754  xor     ecx, ecx
0x180013756  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001375c  lea     rdx, aTheQueryString; "The query string for a copyright reques"...
0x180013763  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180013767  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18001376c  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180013773  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180013777  call    _CxxThrowException_0
0x18001377d  cmp     byte ptr [rbx+40h], 0
0x180013781  jz      short loc_1800137EA
0x180013783  mov     r8d, 0E2h
0x180013789  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18001378d  mov     rcx, rbx; this
0x180013790  call    ?GetValueFromConfig@CopyrightRequest@BingOnlineServices@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationManagerKeys@@@Z; BingOnlineServices::CopyrightRequest::GetValueFromConfig(ConfigurationManagerKeys)
0x180013795  mov     rdx, rax
0x180013798  lea     rcx, [rbp+4Fh+var_98]
0x18001379c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800137a1  lea     rcx, [rbp+4Fh+pExceptionObject]
0x1800137a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800137aa  lea     rcx, [rbp+4Fh+var_70]
0x1800137ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800137b3  nop
0x1800137b4  lea     r8, [rbx+20h]
0x1800137b8  mov     [rsp+100h+var_E0], rax
0x1800137bd  mov     r9, rbx
0x1800137c0  lea     rdx, [rbp+4Fh+var_98]
0x1800137c4  lea     rcx, [rbp+4Fh+pExceptionObject]
0x1800137c8  call    ?ReplaceFragmentUri@ServiceRequestHelper@BingOnlineServices@@SA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@000@Z; BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800137cd  nop
0x1800137ce  mov     rdx, rax
0x1800137d1  lea     rcx, [rbp+4Fh+var_98]
0x1800137d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800137da  nop
0x1800137db  lea     rcx, [rbp+4Fh+pExceptionObject]
0x1800137df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800137e4  nop
0x1800137e5  jmp     loc_1800138AE
0x1800137ea  movups  xmm0, xmmword ptr [r9]
0x1800137ee  movaps  [rbp+4Fh+var_70], xmm0
0x1800137f2  movups  xmm1, xmmword ptr [r9+10h]
0x1800137f7  movaps  [rbp+4Fh+var_60], xmm1
0x1800137fb  movups  xmm0, xmmword ptr [r9+20h]
0x180013800  movaps  [rbp+4Fh+var_50], xmm0
0x180013804  lea     rcx, [rbp+4Fh+var_70]
0x180013808  call    ?IsValid@BoundingBox@BingOnlineServices@@SA_NU12@@Z; BingOnlineServices::BoundingBox::IsValid(BingOnlineServices::BoundingBox)
0x18001380d  test    al, al
0x18001380f  jnz     short loc_180013856
0x180013811  lea     rax, aFailedToSpecif_0; "Failed to specify valid bounding box"
0x180013818  mov     [rsp+100h+var_E0], rax
0x18001381d  mov     r9, rbx
0x180013820  mov     r8d, 2Ch ; ','
0x180013826  lea     rdx, aBingonlineserv_0; "BingOnlineServices::CopyrightRequest::E"...
0x18001382d  xor     ecx, ecx
0x18001382f  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180013835  lea     rdx, aTheBoundingBox; "The bounding box for a copyright reques"...
0x18001383c  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180013840  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180013845  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18001384c  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180013850  call    _CxxThrowException_0
0x180013856  mov     r8d, 0E1h
0x18001385c  lea     rdx, [rbp+4Fh+var_70]
0x180013860  mov     rcx, rbx; this
0x180013863  call    ?GetValueFromConfig@CopyrightRequest@BingOnlineServices@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationManagerKeys@@@Z; BingOnlineServices::CopyrightRequest::GetValueFromConfig(ConfigurationManagerKeys)
0x180013868  mov     rdx, rax
0x18001386b  lea     rcx, [rbp+4Fh+var_98]
0x18001386f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180013874  lea     rcx, [rbp+4Fh+var_70]
0x180013878  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001387d  lea     r8, [rbx+20h]
0x180013881  mov     [rsp+100h+var_D0], r15d
0x180013886  mov     [rsp+100h+var_D8], rsi
0x18001388b  mov     [rsp+100h+var_E0], r14
0x180013890  mov     r9, rbx
0x180013893  lea     rdx, [rbp+4Fh+var_98]
0x180013897  lea     rcx, [rbp+4Fh+var_70]
0x18001389b  call    ?ReplaceFragmentUri@ServiceRequestHelper@BingOnlineServices@@SA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@000AEBUBoundingBox@2@I@Z; BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,BingOnlineServices::BoundingBox const &,uint)
0x1800138a0  nop
0x1800138a1  mov     rdx, rax
0x1800138a4  lea     rcx, [rbp+4Fh+var_98]
0x1800138a8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800138ad  nop
0x1800138ae  lea     rcx, [rbp+4Fh+var_70]
0x1800138b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800138b7  lea     rax, aExecutingCopyr; "Executing copyright request"
0x1800138be  mov     [rsp+100h+var_E0], rax
0x1800138c3  mov     r9, rbx
0x1800138c6  mov     r8d, 33h ; '3'
0x1800138cc  lea     rdx, aBingonlineserv_0; "BingOnlineServices::CopyrightRequest::E"...
0x1800138d3  lea     ecx, [r8-2Eh]
0x1800138d7  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x1800138dd  lea     rdx, [rbp+4Fh+var_98]
0x1800138e1  lea     rcx, [rbp+4Fh+pExceptionObject]
0x1800138e5  call    ?MakeJsonRequestAsync@ServiceRequestHelper@BingOnlineServices@@SA?AV?$task@UOnlineServiceResponse@BingOnlineServices@@@pplx@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync(std::wstring const &)
0x1800138ea  nop
0x1800138eb  mov     rdx, rdi
0x1800138ee  mov     rcx, rax
0x1800138f1  call    pplx__task_BingOnlineServices__OnlineServiceResponse___then__lambda_5d9e762188e201a51595a856687dbe89___
0x1800138f6  nop
0x1800138f7  mov     rcx, [rbp+4Fh+var_B0]; this
0x1800138fb  test    rcx, rcx
0x1800138fe  jz      short loc_180013906
0x180013900  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180013905  nop
0x180013906  lea     rcx, [rbp+4Fh+var_98]
0x18001390a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001390f  mov     rax, rdi
0x180013912  mov     rcx, [rbp+4Fh+var_40]
0x180013916  xor     rcx, rsp; StackCookie
0x180013919  call    __security_check_cookie
0x18001391e  add     rsp, 0D8h
0x180013925  pop     r15
0x180013927  pop     r14
0x180013929  pop     rdi
0x18001392a  pop     rsi
0x18001392b  pop     rbx
0x18001392c  pop     rbp
0x18001392d  retn
```
