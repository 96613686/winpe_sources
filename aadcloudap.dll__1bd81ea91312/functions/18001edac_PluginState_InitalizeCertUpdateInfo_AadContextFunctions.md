# PluginState::InitalizeCertUpdateInfo(AadContextFunctions *)

- ea: `0x18001edac`
- end: `0x18001ef4c`
- name: `?InitalizeCertUpdateInfo@PluginState@@QEAAJPEAVAadContextFunctions@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(PluginState *__hidden this, struct AadContextFunctions *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180017248`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18001edac`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ee95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ee95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eeba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eeba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eecc`

## string_xrefs

- `0x18001edd0`: `PluginState::InitalizeCertUpdateInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PluginState::InitalizeCertUpdateInfo(PluginState *this, struct AadContextFunctions *a2)
{
  signed int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v8; // [rsp+30h] [rbp-58h]
  const char *v9[6]; // [rsp+50h] [rbp-38h] BYREF
  int v10; // [rsp+98h] [rbp+10h] BYREF

  v10 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v9,
    (int)"pluginstate.cpp",
    (int)"PluginState::InitalizeCertUpdateInfo",
    (int)&v10);
  if ( !a2 )
  {
    v4 = -1073741811;
    v10 = -1073741811;
    v8 = 142;
LABEL_11:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v4, "pluginstate.cpp", v8, "NTSTATUS", &base);
    goto LABEL_12;
  }
  *(_QWORD *)(*(_QWORD *)this + 144LL) = (*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64))(*(_QWORD *)a2 + 24LL))(
                                           a2,
                                           24);
  v5 = *(_QWORD *)(*(_QWORD *)this + 144LL);
  if ( !v5 )
  {
    v4 = -1073741801;
    v10 = -1073741801;
    v8 = 148;
    goto LABEL_11;
  }
  *(_OWORD *)v5 = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 144LL) + 8LL) = CreateEventW(0, 0, 0, 0);
  if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 144LL) + 8LL) )
  {
    v4 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v10 = v4;
    if ( v4 < 0 )
    {
      v8 = 156;
      goto LABEL_11;
    }
  }
LABEL_12:
  v6 = v10;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v9);
  return v6;
}

```

## disassembly

```asm
0x18001edac  mov     rax, rsp
0x18001edaf  mov     [rax+8], rbx
0x18001edb3  mov     [rax+18h], rsi
0x18001edb7  push    rdi
0x18001edb8  sub     rsp, 80h
0x18001edbf  mov     rbx, rdx
0x18001edc2  mov     rdi, rcx
0x18001edc5  mov     dword ptr [rax+10h], 0
0x18001edcc  lea     r9, [rax+10h]
0x18001edd0  lea     r8, aPluginstateIni_0; "PluginState::InitalizeCertUpdateInfo"
0x18001edd7  lea     rsi, aOnecoreuapDsEx_57+21h; "pluginstate.cpp"
0x18001edde  mov     rdx, rsi
0x18001ede1  lea     rcx, [rax-38h]
0x18001ede5  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18001edea  nop
0x18001edeb  test    rbx, rbx
0x18001edee  jnz     short loc_18001EE21
0x18001edf0  mov     eax, 0C000000Dh
0x18001edf5  mov     [rsp+88h+arg_8], eax
0x18001edfc  lea     rcx, base
0x18001ee03  mov     [rsp+88h+var_48], rcx
0x18001ee08  lea     rcx, aNtstatus; "NTSTATUS"
0x18001ee0f  mov     [rsp+88h+var_50], rcx
0x18001ee14  mov     [rsp+88h+var_58], 8Eh
0x18001ee1c  jmp     loc_18001EF05
0x18001ee21  mov     rax, [rbx]
0x18001ee24  mov     edx, 18h
0x18001ee29  mov     rcx, rbx
0x18001ee2c  mov     rax, [rax+18h]
0x18001ee30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee35  mov     rcx, [rdi]
0x18001ee38  mov     [rcx+90h], rax
0x18001ee3f  mov     rax, [rdi]
0x18001ee42  mov     rcx, [rax+90h]
0x18001ee49  test    rcx, rcx
0x18001ee4c  jnz     short loc_18001EE7F
0x18001ee4e  mov     eax, 0C0000017h
0x18001ee53  mov     [rsp+88h+arg_8], eax
0x18001ee5a  lea     rcx, base
0x18001ee61  mov     [rsp+88h+var_48], rcx
0x18001ee66  lea     rcx, aNtstatus; "NTSTATUS"
0x18001ee6d  mov     [rsp+88h+var_50], rcx
0x18001ee72  mov     [rsp+88h+var_58], 94h
0x18001ee7a  jmp     loc_18001EF05
0x18001ee7f  xorps   xmm0, xmm0
0x18001ee82  xor     eax, eax
0x18001ee84  movups  xmmword ptr [rcx], xmm0
0x18001ee87  mov     [rcx+10h], rax
0x18001ee8b  xor     r9d, r9d; lpName
0x18001ee8e  xor     r8d, r8d; bInitialState
0x18001ee91  xor     edx, edx; bManualReset
0x18001ee93  xor     ecx, ecx; lpEventAttributes
0x18001ee95  call    cs:__imp_CreateEventW
0x18001ee9b  mov     rcx, [rdi]
0x18001ee9e  mov     rdx, [rcx+90h]
0x18001eea5  mov     [rdx+8], rax
0x18001eea9  mov     rax, [rdi]
0x18001eeac  mov     rcx, [rax+90h]
0x18001eeb3  cmp     qword ptr [rcx+8], 0
0x18001eeb8  jnz     short loc_18001EF24
0x18001eeba  call    cs:__imp_GetLastError
0x18001eec0  test    eax, eax
0x18001eec2  jg      short loc_18001EECC
0x18001eec4  call    cs:__imp_GetLastError
0x18001eeca  jmp     short loc_18001EEDA
0x18001eecc  call    cs:__imp_GetLastError
0x18001eed2  movzx   eax, ax
0x18001eed5  or      eax, 0C0070000h
0x18001eeda  mov     [rsp+88h+arg_8], eax
0x18001eee1  test    eax, eax
0x18001eee3  jns     short loc_18001EF24
0x18001eee5  lea     rcx, base
0x18001eeec  mov     [rsp+88h+var_48], rcx
0x18001eef1  lea     rcx, aNtstatus; "NTSTATUS"
0x18001eef8  mov     [rsp+88h+var_50], rcx
0x18001eefd  mov     [rsp+88h+var_58], 9Ch
0x18001ef05  mov     [rsp+88h+var_60], rsi
0x18001ef0a  mov     ecx, 2
0x18001ef0f  mov     [rsp+88h+var_68], eax
0x18001ef13  mov     r9d, ecx
0x18001ef16  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18001ef1d  xor     edx, edx
0x18001ef1f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18001ef24  mov     ebx, [rsp+88h+arg_8]
0x18001ef2b  lea     rcx, [rsp+88h+var_38]
0x18001ef30  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18001ef35  mov     eax, ebx
0x18001ef37  lea     r11, [rsp+88h+var_8]
0x18001ef3f  mov     rbx, [r11+10h]
0x18001ef43  mov     rsi, [r11+20h]
0x18001ef47  mov     rsp, r11
0x18001ef4a  pop     rdi
0x18001ef4b  retn
```
