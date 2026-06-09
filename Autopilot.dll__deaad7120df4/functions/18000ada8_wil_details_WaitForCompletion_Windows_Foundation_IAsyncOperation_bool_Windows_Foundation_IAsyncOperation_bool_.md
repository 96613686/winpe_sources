# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::~CompletionDelegate(void)

- ea: `0x18000ada8`
- end: `0x18000ae0d`
- name: `??1CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b7b0`

## callees

- `0x18000ada8`
- `0x180012220`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adba`

## string_xrefs

- `0x18000adfb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::~CompletionDelegate(
        __int64 a1)
{
  void *v2; // rcx
  const char *v3; // r9
  __int64 v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(void **)(a1 + 56);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  *(_DWORD *)(a1 + 44) = -1073741823;
  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x18000ada8  push    rbx
0x18000adaa  sub     rsp, 20h
0x18000adae  mov     rbx, rcx
0x18000adb1  mov     rcx, [rcx+38h]; hObject
0x18000adb5  test    rcx, rcx
0x18000adb8  jz      short loc_18000ADCF
0x18000adba  call    cs:__imp_CloseHandle
0x18000adc1  nop     dword ptr [rax+rax+00h]
0x18000adc6  mov     rcx, [rsp+28h]; this
0x18000adcb  test    eax, eax
0x18000adcd  jz      short loc_18000ADFB
0x18000adcf  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000add6  mov     rcx, [rbx+20h]
0x18000adda  test    rcx, rcx
0x18000addd  jz      short loc_18000ADF4
0x18000addf  mov     qword ptr [rbx+20h], 0
0x18000ade7  mov     rax, [rcx]
0x18000adea  mov     rax, [rax+10h]
0x18000adee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf3  nop
0x18000adf4  add     rsp, 20h
0x18000adf8  pop     rbx
0x18000adf9  retn
0x18000adfb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ae02  mov     edx, 0A0Bh; void *
0x18000ae07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
