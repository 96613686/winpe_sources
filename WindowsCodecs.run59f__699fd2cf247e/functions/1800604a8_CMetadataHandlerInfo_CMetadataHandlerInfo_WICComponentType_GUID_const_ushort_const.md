# CMetadataHandlerInfo::CMetadataHandlerInfo(WICComponentType,_GUID const &,ushort const *)

- ea: `0x1800604a8`
- end: `0x1800605ee`
- name: `??0CMetadataHandlerInfo@@QEAA@W4WICComponentType@@AEBU_GUID@@PEBG@Z`
- size: `326`
- prototype: `CMetadataHandlerInfo *__fastcall(CMetadataHandlerInfo *__hidden this, enum WICComponentType, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800603a0`
- `0x18006108c`
- `0x1800624c0`

## callees

- `0x18002bb8c`
- `0x18005d190`
- `0x1800604a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800605ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800605c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800605ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800605c6`

## string_xrefs

- `0x1800605bc`: `windowscodecs.dll`
- `0x1800605a2`: `windowscodecsext.dll`

## pseudocode

```c
CMetadataHandlerInfo *__fastcall CMetadataHandlerInfo::CMetadataHandlerInfo(
        CMetadataHandlerInfo *this,
        enum WICComponentType a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4)
{
  CComponentInfo::CComponentInfo(this, a2, a3);
  CMTALock::CMTALock((CMetadataHandlerInfo *)((char *)this + 168));
  *(_QWORD *)this = &CMetadataHandlerInfo::`vftable'{for `CRegistryInfo'};
  *((_QWORD *)this + 5) = &CMetadataHandlerInfo::`vftable'{for `IWICComponentInfoInternal'};
  *((_QWORD *)this + 19) = &CMetadataHandlerInfo::`vftable'{for `IWICMetadataReaderInfo'};
  *((_QWORD *)this + 20) = &CMetadataHandlerInfo::`vftable'{for `IWICMetadataWriterInfo'};
  *((_QWORD *)this + 21) = &CMetadataHandlerInfo::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 62) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 38) = (char *)this + 336;
  *((_QWORD *)this + 39) = (char *)this + 336;
  *((_DWORD *)this + 80) = 2;
  *(_QWORD *)((char *)this + 324) = 2;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 118) = 0;
  if ( a4 )
  {
    if ( (unsigned int)_o__wcsicmp(a4, L"windowscodecsext.dll") )
    {
      if ( !(unsigned int)_o__wcsicmp(a4, L"windowscodecs.dll") )
        *((_DWORD *)this + 72) = 1;
    }
    else
    {
      *((_DWORD *)this + 72) = 2;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800604a8  mov     [rsp+arg_0], rbx
0x1800604ad  mov     [rsp+arg_8], rsi
0x1800604b2  push    rdi
0x1800604b3  sub     rsp, 20h
0x1800604b7  mov     rsi, r9
0x1800604ba  mov     rdi, rcx
0x1800604bd  call    ??0CComponentInfo@@QEAA@W4WICComponentType@@AEBU_GUID@@@Z; CComponentInfo::CComponentInfo(WICComponentType,_GUID const &)
0x1800604c2  lea     rbx, [rdi+0A8h]
0x1800604c9  mov     rcx, rbx; this
0x1800604cc  call    ??0CMTALock@@QEAA@XZ; CMTALock::CMTALock(void)
0x1800604d1  lea     rax, ??_7CMetadataHandlerInfo@@6BCRegistryInfo@@@; const CMetadataHandlerInfo::`vftable'{for `CRegistryInfo'}
0x1800604d8  mov     [rdi], rax
0x1800604db  lea     rax, ??_7CMetadataHandlerInfo@@6BIWICComponentInfoInternal@@@; const CMetadataHandlerInfo::`vftable'{for `IWICComponentInfoInternal'}
0x1800604e2  mov     [rdi+28h], rax
0x1800604e6  lea     rax, ??_7CMetadataHandlerInfo@@6BIWICMetadataReaderInfo@@@; const CMetadataHandlerInfo::`vftable'{for `IWICMetadataReaderInfo'}
0x1800604ed  mov     [rdi+98h], rax
0x1800604f4  lea     rax, ??_7CMetadataHandlerInfo@@6BIWICMetadataWriterInfo@@@; const CMetadataHandlerInfo::`vftable'{for `IWICMetadataWriterInfo'}
0x1800604fb  mov     [rdi+0A0h], rax
0x180060502  lea     rax, ??_7CMetadataHandlerInfo@@6BCMTALock@@@; const CMetadataHandlerInfo::`vftable'{for `CMTALock'}
0x180060509  mov     [rbx], rax
0x18006050c  xor     ebx, ebx
0x18006050e  mov     [rdi+0F0h], rbx
0x180060515  lea     rax, [rdi+150h]
0x18006051c  mov     [rdi+0F8h], ebx
0x180060522  mov     [rdi+100h], rbx
0x180060529  mov     [rdi+108h], rbx
0x180060530  mov     [rdi+110h], rbx
0x180060537  mov     [rdi+118h], rbx
0x18006053e  mov     [rdi+120h], rbx
0x180060545  mov     [rdi+128h], ebx
0x18006054b  mov     [rdi+130h], rax
0x180060552  mov     [rdi+138h], rax
0x180060559  mov     dword ptr [rdi+140h], 2
0x180060563  mov     qword ptr [rdi+144h], 2
0x18006056e  mov     [rdi+1C0h], rbx
0x180060575  mov     [rdi+1C8h], rbx
0x18006057c  mov     [rdi+1D0h], rbx
0x180060583  mov     [rdi+1D8h], ebx
0x180060589  test    rsi, rsi
0x18006058c  jnz     short loc_1800605A2
0x18006058e  mov     rbx, [rsp+28h+arg_0]
0x180060593  mov     rax, rdi
0x180060596  mov     rsi, [rsp+28h+arg_8]
0x18006059b  add     rsp, 20h
0x18006059f  pop     rdi
0x1800605a0  retn
0x1800605a2  lea     rdx, aWindowscodecse_0; "windowscodecsext.dll"
0x1800605a9  mov     rcx, rsi
0x1800605ac  call    cs:__imp__o__wcsicmp
0x1800605b3  nop     dword ptr [rax+rax+00h]
0x1800605b8  test    eax, eax
0x1800605ba  jz      short loc_1800605E2
0x1800605bc  lea     rdx, aWindowscodecsD_0; "windowscodecs.dll"
0x1800605c3  mov     rcx, rsi
0x1800605c6  call    cs:__imp__o__wcsicmp
0x1800605cd  nop     dword ptr [rax+rax+00h]
0x1800605d2  test    eax, eax
0x1800605d4  jnz     short loc_18006058E
0x1800605d6  mov     dword ptr [rdi+120h], 1
0x1800605e0  jmp     short loc_18006058E
0x1800605e2  mov     dword ptr [rdi+120h], 2
0x1800605ec  jmp     short loc_18006058E
```
