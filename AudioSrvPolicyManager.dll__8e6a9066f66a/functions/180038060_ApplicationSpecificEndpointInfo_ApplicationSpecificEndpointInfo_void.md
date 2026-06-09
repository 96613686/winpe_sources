# ApplicationSpecificEndpointInfo::~ApplicationSpecificEndpointInfo(void)

- ea: `0x180038060`
- end: `0x18003810e`
- name: `??1ApplicationSpecificEndpointInfo@@UEAA@XZ`
- size: `174`
- prototype: `void __fastcall(ApplicationSpecificEndpointInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038420`

## callees

- `0x18000ac00`
- `0x180031984`
- `0x180038060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800380fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800380fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380c0`

## pseudocode

```c
void __fastcall ApplicationSpecificEndpointInfo::~ApplicationSpecificEndpointInfo(
        ApplicationSpecificEndpointInfo *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &ApplicationSpecificEndpointInfo::`vftable';
  `eh vector destructor iterator'(
    (char *)this + 144,
    8u,
    6u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector destructor iterator'(
    (char *)this + 96,
    8u,
    6u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
  {
    std::_Deallocate<16>(v4, (*((_QWORD *)this + 9) - v4) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180038060  push    rbx
0x180038062  sub     rsp, 20h
0x180038066  mov     rbx, rcx
0x180038069  lea     rax, ??_7ApplicationSpecificEndpointInfo@@6B@; const ApplicationSpecificEndpointInfo::`vftable'
0x180038070  mov     [rcx], rax
0x180038073  add     rcx, 90h; void *
0x18003807a  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180038081  mov     edx, 8; unsigned __int64
0x180038086  lea     r8d, [rdx-2]; unsigned __int64
0x18003808a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003808f  lea     rcx, [rbx+60h]; void *
0x180038093  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18003809a  mov     edx, 8; unsigned __int64
0x18003809f  lea     r8d, [rdx-2]; unsigned __int64
0x1800380a3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800380a8  mov     rcx, [rbx+58h]; pv
0x1800380ac  test    rcx, rcx
0x1800380af  jz      short loc_1800380B7
0x1800380b1  call    cs:__imp_CoTaskMemFree
0x1800380b7  mov     rcx, [rbx+50h]; pv
0x1800380bb  test    rcx, rcx
0x1800380be  jz      short loc_1800380C6
0x1800380c0  call    cs:__imp_CoTaskMemFree
0x1800380c6  mov     rcx, [rbx+38h]
0x1800380ca  test    rcx, rcx
0x1800380cd  jz      short loc_1800380F7
0x1800380cf  mov     rdx, [rbx+48h]
0x1800380d3  sub     rdx, rcx
0x1800380d6  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800380da  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800380df  mov     qword ptr [rbx+38h], 0
0x1800380e7  mov     qword ptr [rbx+40h], 0
0x1800380ef  mov     qword ptr [rbx+48h], 0
0x1800380f7  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800380fb  call    cs:__imp_DeleteCriticalSection
0x180038101  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180038108  add     rsp, 20h
0x18003810c  pop     rbx
0x18003810d  retn
```
