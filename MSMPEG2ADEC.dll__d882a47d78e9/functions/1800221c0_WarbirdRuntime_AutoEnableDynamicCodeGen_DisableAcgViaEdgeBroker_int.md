# WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaEdgeBroker(int)

- ea: `0x1800221c0`
- end: `0x180022320`
- name: `?DisableAcgViaEdgeBroker@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NH@Z`
- size: `352`
- prototype: `bool __fastcall(WarbirdRuntime::AutoEnableDynamicCodeGen *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f500`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x1800221c0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180022264`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180022264`

## string_xrefs

- `0x180022205`: `Windows.Internal.SecurityMitigationsBroker`

## pseudocode

```c
__int64 __fastcall WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaEdgeBroker(
        WarbirdRuntime::AutoEnableDynamicCodeGen *this)
{
  unsigned __int8 v1; // bl
  __int64 v2; // rdx
  __int64 v4; // [rsp+20h] [rbp-258h] BYREF
  __int64 v5; // [rsp+28h] [rbp-250h] BYREF
  __int64 v6; // [rsp+30h] [rbp-248h] BYREF
  GUID v7; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-228h] BYREF

  v7 = GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5;
  memset_0(Filename, 0, 0x208u);
  v5 = 0;
  v6 = 0;
  v4 = 0;
  v1 = 0;
  if ( (int)((__int64 (__fastcall *)(const wchar_t *, __int64, __int64 *))WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc)(
              L"Windows.Internal.SecurityMitigationsBroker",
              42,
              &v4) >= 0
    && (int)((__int64 (__fastcall *)(__int64, GUID *, __int64 *))WarbirdRuntime::AutoEnableDynamicCodeGen::RoGetActivationFactoryProc)(
              v4,
              &v7,
              &v6) >= 0 )
  {
    if ( GetModuleFileNameW(&_ImageBase, Filename, 0x104u) )
    {
      v2 = -1;
      do
        ++v2;
      while ( Filename[v2] );
      if ( (int)((__int64 (__fastcall *)(WCHAR *, __int64, __int64 *))WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc)(
                  Filename,
                  v2,
                  &v5) >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 56LL))(v6, v5);
        v1 = 1;
      }
    }
  }
  if ( v4 )
    ((void (*)(void))WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsDeleteStringProc)();
  if ( v5 )
    ((void (*)(void))WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsDeleteStringProc)();
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v1;
}

```

## disassembly

```asm
0x1800221c0  push    rbx
0x1800221c2  sub     rsp, 270h
0x1800221c9  mov     rax, cs:__security_cookie
0x1800221d0  xor     rax, rsp
0x1800221d3  mov     [rsp+278h+var_18], rax
0x1800221db  movups  xmm0, xmmword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data1
0x1800221e2  xor     edx, edx; Val
0x1800221e4  lea     rcx, [rsp+278h+Filename]; void *
0x1800221e9  mov     r8d, 208h; Size
0x1800221ef  movups  xmmword ptr [rsp+278h+var_240.Data1], xmm0
0x1800221f4  call    memset_0
0x1800221f9  xor     eax, eax
0x1800221fb  lea     r8, [rsp+278h+var_258]
0x180022200  mov     [rsp+278h+var_250], rax
0x180022205  lea     rcx, ?arrClassId@?1??DisableAcgViaEdgeBroker@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NH@Z@4QBGB; "Windows.Internal.SecurityMitigationsBro"...
0x18002220c  mov     [rsp+278h+var_248], rax
0x180022211  mov     edx, 2Ah ; '*'
0x180022216  mov     [rsp+278h+var_258], rax
0x18002221b  xor     bl, bl
0x18002221d  mov     rax, cs:?WindowsCreateStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEBGIPEAPEAX@ZEA; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc)(ushort const *,uint,void * *)
0x180022224  call    cs:__guard_dispatch_icall_fptr
0x18002222a  test    eax, eax
0x18002222c  js      loc_1800222BE
0x180022232  mov     rcx, [rsp+278h+var_258]
0x180022237  lea     r8, [rsp+278h+var_248]
0x18002223c  mov     rax, cs:?RoGetActivationFactoryProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEAXAEBU_GUID@@PEAPEAX@ZEA; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::RoGetActivationFactoryProc)(void *,_GUID const &,void * *)
0x180022243  lea     rdx, [rsp+278h+var_240]
0x180022248  call    cs:__guard_dispatch_icall_fptr
0x18002224e  test    eax, eax
0x180022250  js      short loc_1800222BE
0x180022252  mov     r8d, 104h; nSize
0x180022258  lea     rdx, [rsp+278h+Filename]; lpFilename
0x18002225d  lea     rcx, __ImageBase; hModule
0x180022264  call    cs:__imp_GetModuleFileNameW
0x18002226b  nop     dword ptr [rax+rax+00h]
0x180022270  test    eax, eax
0x180022272  jz      short loc_1800222BE
0x180022274  lea     rax, [rsp+278h+Filename]
0x180022279  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180022280  inc     rdx
0x180022283  cmp     word ptr [rax+rdx*2], 0
0x180022288  jnz     short loc_180022280
0x18002228a  mov     rax, cs:?WindowsCreateStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEBGIPEAPEAX@ZEA; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc)(ushort const *,uint,void * *)
0x180022291  lea     r8, [rsp+278h+var_250]
0x180022296  lea     rcx, [rsp+278h+Filename]
0x18002229b  call    cs:__guard_dispatch_icall_fptr
0x1800222a1  test    eax, eax
0x1800222a3  js      short loc_1800222BE
0x1800222a5  mov     rcx, [rsp+278h+var_248]
0x1800222aa  mov     rdx, [rsp+278h+var_250]
0x1800222af  mov     rax, [rcx]
0x1800222b2  mov     rax, [rax+38h]
0x1800222b6  call    cs:__guard_dispatch_icall_fptr
0x1800222bc  mov     bl, 1
0x1800222be  mov     rcx, [rsp+278h+var_258]
0x1800222c3  test    rcx, rcx
0x1800222c6  jz      short loc_1800222D5
0x1800222c8  mov     rax, cs:?WindowsDeleteStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEAX@ZEA; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsDeleteStringProc)(void *)
0x1800222cf  call    cs:__guard_dispatch_icall_fptr
0x1800222d5  mov     rcx, [rsp+278h+var_250]
0x1800222da  test    rcx, rcx
0x1800222dd  jz      short loc_1800222EC
0x1800222df  mov     rax, cs:?WindowsDeleteStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEAX@ZEA; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsDeleteStringProc)(void *)
0x1800222e6  call    cs:__guard_dispatch_icall_fptr
0x1800222ec  mov     rcx, [rsp+278h+var_248]
0x1800222f1  test    rcx, rcx
0x1800222f4  jz      short loc_180022303
0x1800222f6  mov     rdx, [rcx]
0x1800222f9  mov     rax, [rdx+10h]
0x1800222fd  call    cs:__guard_dispatch_icall_fptr
0x180022303  movzx   eax, bl
0x180022306  mov     rcx, [rsp+278h+var_18]
0x18002230e  xor     rcx, rsp; StackCookie
0x180022311  call    __security_check_cookie
0x180022316  add     rsp, 270h
0x18002231d  pop     rbx
0x18002231e  retn
```
