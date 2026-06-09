# Apx::ApfIpcIoLinkMgr::AcquireQueryRemoveOffReference(void)

- ea: `0x180025ab0`
- end: `0x180025af8`
- name: `?AcquireQueryRemoveOffReference@ApfIpcIoLinkMgr@Apx@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(Apx::ApfIpcIoLinkMgr *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180025ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ae0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025acb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025acb`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLinkMgr::AcquireQueryRemoveOffReference(Apx::ApfIpcIoLinkMgr *this)
{
  unsigned int v2; // edi

  v2 = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_BYTE *)this + 117) )
  {
    ++*((_DWORD *)this + 28);
    v2 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v2;
}

```

## disassembly

```asm
0x180025ab0  mov     [rsp+arg_0], rbx
0x180025ab5  mov     [rsp+arg_8], rsi
0x180025aba  push    rdi
0x180025abb  sub     rsp, 20h
0x180025abf  mov     rbx, rcx
0x180025ac2  mov     edi, 80004005h
0x180025ac7  add     rcx, 10h; lpCriticalSection
0x180025acb  call    cs:__imp_EnterCriticalSection
0x180025ad1  cmp     byte ptr [rbx+75h], 0
0x180025ad5  jnz     short loc_180025ADC
0x180025ad7  inc     dword ptr [rbx+70h]
0x180025ada  xor     edi, edi
0x180025adc  lea     rcx, [rbx+10h]; lpCriticalSection
0x180025ae0  call    cs:__imp_LeaveCriticalSection
0x180025ae6  mov     rbx, [rsp+28h+arg_0]
0x180025aeb  mov     eax, edi
0x180025aed  mov     rsi, [rsp+28h+arg_8]
0x180025af2  add     rsp, 20h
0x180025af6  pop     rdi
0x180025af7  retn
```
