# Microsoft::Diagnostics::UtcDecoderHostApiManager::~UtcDecoderHostApiManager(void)

- ea: `0x14000fa04`
- end: `0x14000fa51`
- name: `??1UtcDecoderHostApiManager@Diagnostics@Microsoft@@QEAA@XZ`
- size: `77`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140010fd4`
- `0x140017b00`

## callees

- `0x1400088f4`
- `0x14000f6cc`
- `0x14000fa04`
- `0x140011194`
- `0x1400116c0`

## string_xrefs

- `0x14000fa1b`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`

## pseudocode

```c
void __fastcall Microsoft::Diagnostics::UtcDecoderHostApiManager::~UtcDecoderHostApiManager(void **this)
{
  int v2; // eax
  void *v3; // rcx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer((Microsoft::Diagnostics::UtcDecoderHostApiManager *)this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
      (const char *)(unsigned int)v2,
      v4);
  std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>(this + 2);
  v3 = this[1];
  if ( v3 )
    operator delete(v3, 1u);
}

```

## disassembly

```asm
0x14000fa04  push    rbx; int
0x14000fa06  sub     rsp, 20h
0x14000fa0a  mov     rbx, rcx
0x14000fa0d  call    ?StopServer@UtcDecoderHostApiManager@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer(void)
0x14000fa12  test    eax, eax
0x14000fa14  jns     short loc_14000FA2F
0x14000fa16  mov     rcx, [rsp+28h]; this
0x14000fa1b  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x14000fa22  mov     r9d, eax; char *
0x14000fa25  mov     edx, 1Dh; void *
0x14000fa2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000fa2f  lea     rcx, [rbx+10h]
0x14000fa33  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>(void)
0x14000fa38  mov     rcx, [rbx+8]; void *
0x14000fa3c  test    rcx, rcx
0x14000fa3f  jz      short loc_14000FA4B
0x14000fa41  mov     edx, 1; unsigned __int64
0x14000fa46  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fa4b  add     rsp, 20h
0x14000fa4f  pop     rbx
0x14000fa50  retn
```
