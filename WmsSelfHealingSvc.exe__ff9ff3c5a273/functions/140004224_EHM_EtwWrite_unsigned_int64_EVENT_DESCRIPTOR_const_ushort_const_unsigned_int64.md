# __EHM_EtwWrite(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)

- ea: `0x140004224`
- end: `0x140004282`
- name: `?__EHM_EtwWrite@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEBG0@Z`
- size: `94`
- prototype: `void __fastcall(__int64, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400036d8`
- `0x140003948`

## callees

- `0x140004224`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14000426a`
- `ADVAPI32!EventWrite` at `0x14000426a`

## pseudocode

```c
void __fastcall __EHM_EtwWrite(__int64 a1, const struct _EVENT_DESCRIPTOR *a2, const unsigned __int16 *a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF

  if ( g_hEventProviderHandle )
  {
    UserData.Ptr = (ULONGLONG)a3;
    UserData.Size = 2 * a4;
    UserData.Reserved = 0;
    EventWrite(g_hEventProviderHandle, &WMS_Trace, 1u, &UserData);
  }
}

```

## disassembly

```asm
0x140004224  sub     rsp, 48h
0x140004228  mov     rax, cs:__security_cookie
0x14000422f  xor     rax, rsp
0x140004232  mov     [rsp+48h+var_18], rax
0x140004237  mov     rcx, cs:?g_hEventProviderHandle@@3_KA; RegHandle
0x14000423e  test    rcx, rcx
0x140004241  jz      short loc_140004270
0x140004243  lea     eax, [r9+r9]
0x140004247  mov     [rsp+48h+UserData.Ptr], r8
0x14000424c  lea     r9, [rsp+48h+UserData]; UserData
0x140004251  mov     [rsp+48h+UserData.Size], eax
0x140004255  mov     r8d, 1; UserDataCount
0x14000425b  mov     dword ptr [rsp+48h+UserData.0Ch], 0
0x140004263  lea     rdx, WMS_Trace; EventDescriptor
0x14000426a  call    cs:__imp_EventWrite
0x140004270  mov     rcx, [rsp+48h+var_18]
0x140004275  xor     rcx, rsp; StackCookie
0x140004278  call    __security_check_cookie
0x14000427d  add     rsp, 48h
0x140004281  retn
```
