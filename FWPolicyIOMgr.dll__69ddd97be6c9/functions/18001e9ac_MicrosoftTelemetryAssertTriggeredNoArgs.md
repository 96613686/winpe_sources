# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001e9ac`
- end: `0x18001ea4e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `119`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022b0`
- `0x180003680`
- `0x180004320`
- `0x1800044f0`
- `0x1800046c8`
- `0x180004874`
- `0x1800049e0`
- `0x180004c34`
- `0x180004e04`
- `0x180005360`
- `0x180005d20`
- `0x180007a30`
- `0x1800090fc`
- `0x180009260`
- `0x180009324`
- `0x180009a3c`
- `0x180009d7c`
- `0x180009f80`
- `0x18000a174`
- `0x18000a1f0`
- `0x18000a328`
- `0x18000c310`
- `0x18000d290`
- `0x18000de3c`
- `0x18000e010`
- `0x18000e150`
- `0x18000e274`
- `0x18000e350`
- `0x18000e4c4`
- `0x18000e684`
- `0x18000e844`
- `0x18000e964`
- `0x18000eb5c`
- `0x18000ec70`
- `0x18000ed84`
- `0x180011754`
- `0x180013d14`
- `0x180013edc`
- `0x1800151e8`
- `0x18001569c`
- `0x180015f00`
- `0x18001629c`
- `0x180016930`
- `0x18001777c`
- `0x1800179e4`
- `0x180017a78`
- `0x180018db0`
- `0x18001a290`
- `0x18001a718`
- `0x18001ac50`

## callees

- `0x18001e9ac`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e9e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e9e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001e9cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001e9cd`

## string_xrefs

- `0x18001e9c1`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v3; // [rsp+30h] [rbp-30h]
  __int64 v4; // [rsp+40h] [rbp-20h]
  __int64 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+50h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+68h] [rbp+8h]
  HMODULE phModule; // [rsp+70h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v6 = 1;
        v2[1] = _ImageBase;
        v3 = retaddr;
        v5 = -1;
        v2[0] = 11;
        v4 = 0;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18001e9ac  push    rbp
0x18001e9ae  mov     rbp, rsp
0x18001e9b1  sub     rsp, 60h
0x18001e9b5  lea     r8, [rbp+phModule]; phModule
0x18001e9b9  mov     [rbp+phModule], 0
0x18001e9c1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001e9c8  mov     ecx, 2; dwFlags
0x18001e9cd  call    cs:__imp_GetModuleHandleExA
0x18001e9d3  test    eax, eax
0x18001e9d5  jz      short loc_18001EA48
0x18001e9d7  mov     rcx, [rbp+phModule]; hModule
0x18001e9db  test    rcx, rcx
0x18001e9de  jz      short loc_18001EA48
0x18001e9e0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001e9e7  call    cs:__imp_GetProcAddress
0x18001e9ed  mov     rdx, rax
0x18001e9f0  test    rax, rax
0x18001e9f3  jz      short loc_18001EA48
0x18001e9f5  xor     eax, eax
0x18001e9f7  lea     rcx, [rbp+var_40]
0x18001e9fb  mov     [rbp+var_10], eax
0x18001e9fe  xorps   xmm0, xmm0
0x18001ea01  movups  [rbp+var_20], xmm0
0x18001ea05  lea     rax, __ImageBase
0x18001ea0c  movups  [rbp+var_40], xmm0
0x18001ea10  mov     qword ptr [rbp+var_40+8], rax
0x18001ea14  mov     rax, [rbp+8]
0x18001ea18  movups  [rbp+var_30], xmm0
0x18001ea1c  mov     qword ptr [rbp+var_30], rax
0x18001ea20  or      eax, 0FFFFFFFFh
0x18001ea23  mov     dword ptr [rbp+var_20+8], eax
0x18001ea26  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001ea29  mov     rax, rdx
0x18001ea2c  mov     dword ptr [rbp+var_40], 0Bh
0x18001ea33  mov     byte ptr [rbp+var_10], 1
0x18001ea37  mov     byte ptr [rbp+var_30+8], 0
0x18001ea3b  mov     qword ptr [rbp+var_20], 0
0x18001ea43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea48  add     rsp, 60h
0x18001ea4c  pop     rbp
0x18001ea4d  retn
```
