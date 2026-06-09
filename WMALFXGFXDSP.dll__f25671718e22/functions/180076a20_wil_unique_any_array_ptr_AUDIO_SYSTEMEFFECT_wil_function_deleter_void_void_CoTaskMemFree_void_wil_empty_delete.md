# wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)

- ea: `0x180076a20`
- end: `0x180076a4c`
- name: `??1?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800775a0`

## callees

- `0x180076a20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076a31`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180076a20  push    rbx
0x180076a22  sub     rsp, 20h
0x180076a26  mov     rbx, rcx
0x180076a29  mov     rcx, [rcx]; pv
0x180076a2c  test    rcx, rcx
0x180076a2f  jz      short loc_180076A46
0x180076a31  call    cs:__imp_CoTaskMemFree
0x180076a37  mov     qword ptr [rbx], 0
0x180076a3e  mov     qword ptr [rbx+8], 0
0x180076a46  add     rsp, 20h
0x180076a4a  pop     rbx
0x180076a4b  retn
```
