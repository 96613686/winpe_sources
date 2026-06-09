# MessagingService::OnStopping(int)

- ea: `0x180003500`
- end: `0x1800035c0`
- name: `?OnStopping@MessagingService@@UEAAJH@Z`
- size: `192`
- prototype: `__int64 __fastcall(MessagingService *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000108c`
- `0x180003500`
- `0x180004984`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800035a5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800035a5`

## pseudocode

```c
__int64 __fastcall MessagingService::OnStopping(MessagingService *this, int a2)
{
  TransportManager *v3; // rcx
  __int64 v4; // rcx
  bool v6; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-40h] BYREF
  bool *v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-18h]

  if ( (unsigned int)dword_180013018 > 4 )
  {
    v9 = 1;
    v8 = &v6;
    v6 = a2 != 0;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_18001010B, 0, 0, 3u, &v7);
  }
  v3 = (TransportManager *)*((_QWORD *)this + 24);
  if ( v3 )
  {
    TransportManager::Shutdown(v3);
    v4 = *((_QWORD *)this + 24);
    if ( v4 )
    {
      *((_QWORD *)this + 24) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  if ( g_dllResource )
    FreeLibrary(g_dllResource);
  return 0;
}

```

## disassembly

```asm
0x180003500  mov     r11, rsp
0x180003503  push    rbx
0x180003504  sub     rsp, 70h
0x180003508  mov     rax, cs:__security_cookie
0x18000350f  xor     rax, rsp
0x180003512  mov     [rsp+78h+var_10], rax
0x180003517  mov     eax, cs:dword_180013018
0x18000351d  mov     rbx, rcx
0x180003520  cmp     eax, 4
0x180003523  jbe     short loc_180003565
0x180003525  lea     rax, [r11-48h]
0x180003529  mov     qword ptr [r11-18h], 1
0x180003531  test    edx, edx
0x180003533  mov     [r11-20h], rax
0x180003537  lea     rax, [r11-40h]
0x18000353b  setnz   [rsp+78h+var_48]
0x180003540  mov     [r11-50h], rax
0x180003544  xor     r9d, r9d; int
0x180003547  mov     [rsp+78h+var_58], 3; ULONG
0x18000354f  xor     r8d, r8d; int
0x180003552  lea     rdx, byte_18001010B; int
0x180003559  lea     rcx, dword_180013018; int
0x180003560  call    _tlgWriteTransfer_EventWriteTransfer
0x180003565  mov     rcx, [rbx+0C0h]; this
0x18000356c  test    rcx, rcx
0x18000356f  jz      short loc_180003599
0x180003571  call    ?Shutdown@TransportManager@@QEAAXXZ; TransportManager::Shutdown(void)
0x180003576  mov     rcx, [rbx+0C0h]
0x18000357d  test    rcx, rcx
0x180003580  jz      short loc_180003599
0x180003582  mov     qword ptr [rbx+0C0h], 0
0x18000358d  mov     rax, [rcx]
0x180003590  mov     rax, [rax+10h]
0x180003594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003599  mov     rcx, cs:?g_dllResource@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800035a0  test    rcx, rcx
0x1800035a3  jz      short loc_1800035AB
0x1800035a5  call    cs:__imp_FreeLibrary
0x1800035ab  xor     eax, eax
0x1800035ad  mov     rcx, [rsp+78h+var_10]
0x1800035b2  xor     rcx, rsp; StackCookie
0x1800035b5  call    __security_check_cookie
0x1800035ba  add     rsp, 70h
0x1800035be  pop     rbx
0x1800035bf  retn
```
