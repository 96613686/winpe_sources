# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,char const *)

- ea: `0x140003840`
- end: `0x14000394d`
- name: `??$AddColumnToCoalescedEvent@PEBD@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGPEBD@Z`
- size: `269`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, const CHAR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004f38`
- `0x14000732c`
- `0x14000c3d8`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x140003840`
- `0x140003954`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038f7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400038ba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400038ba`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        const CHAR *a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  signed int LastError; // eax
  __int64 v11; // rcx
  _QWORD v13[2]; // [rsp+30h] [rbp-1D8h] BYREF
  WCHAR WideCharStr[200]; // [rsp+40h] [rbp-1C8h] BYREF

  v13[1] = a2;
  if ( *a2 && a3 && a4 )
  {
    memset_0(WideCharStr, 0, sizeof(WideCharStr));
    if ( MultiByteToWideChar(0, 0, a4, -1, WideCharStr, 200) )
    {
      v8 = *a2;
      v13[0] = v8;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *>(
             a1,
             v13,
             a3,
             WideCharStr);
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  v11 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v9;
}

```

## disassembly

```asm
0x140003840  push    rbx
0x140003842  push    rbp
0x140003843  push    rsi
0x140003844  push    rdi
0x140003845  sub     rsp, 1E8h
0x14000384c  mov     rax, cs:__security_cookie
0x140003853  xor     rax, rsp
0x140003856  mov     [rsp+208h+var_38], rax
0x14000385e  mov     rsi, r9
0x140003861  mov     rbx, r8
0x140003864  mov     rdi, rdx
0x140003867  mov     rbp, rcx
0x14000386a  mov     [rsp+208h+var_1D0], rdx
0x14000386f  cmp     qword ptr [rdx], 0
0x140003873  jz      loc_14000390E
0x140003879  test    rbx, rbx
0x14000387c  jz      loc_14000390E
0x140003882  test    r9, r9
0x140003885  jz      loc_14000390E
0x14000388b  xor     edx, edx; Val
0x14000388d  mov     r8d, 190h; Size
0x140003893  lea     rcx, [rsp+208h+WideCharStr]; void *
0x140003898  call    memset_0
0x14000389d  mov     [rsp+208h+cchWideChar], 0C8h; cchWideChar
0x1400038a5  lea     rax, [rsp+208h+WideCharStr]
0x1400038aa  mov     [rsp+208h+lpWideCharStr], rax; lpWideCharStr
0x1400038af  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1400038b3  mov     r8, rsi; lpMultiByteStr
0x1400038b6  xor     edx, edx; dwFlags
0x1400038b8  xor     ecx, ecx; CodePage
0x1400038ba  call    cs:__imp_MultiByteToWideChar
0x1400038c0  test    eax, eax
0x1400038c2  jz      short loc_1400038F7
0x1400038c4  mov     rcx, [rdi]
0x1400038c7  mov     [rsp+208h+var_1D8], rcx
0x1400038cc  test    rcx, rcx
0x1400038cf  jz      short loc_1400038DE
0x1400038d1  mov     rax, [rcx]
0x1400038d4  mov     rax, [rax+8]
0x1400038d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038dd  nop
0x1400038de  lea     r9, [rsp+208h+WideCharStr]
0x1400038e3  mov     r8, rbx
0x1400038e6  lea     rdx, [rsp+208h+var_1D8]
0x1400038eb  mov     rcx, rbp
0x1400038ee  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x1400038f3  mov     ebx, eax
0x1400038f5  jmp     short loc_140003913
0x1400038f7  call    cs:__imp_GetLastError
0x1400038fd  mov     ebx, eax
0x1400038ff  test    eax, eax
0x140003901  jle     short loc_140003913
0x140003903  movzx   ebx, ax
0x140003906  or      ebx, 80070000h
0x14000390c  jmp     short loc_140003913
0x14000390e  mov     ebx, 80070057h
0x140003913  mov     rcx, [rdi]
0x140003916  test    rcx, rcx
0x140003919  jz      short loc_14000392F
0x14000391b  mov     qword ptr [rdi], 0
0x140003922  mov     rax, [rcx]
0x140003925  mov     rax, [rax+10h]
0x140003929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000392e  nop
0x14000392f  mov     eax, ebx
0x140003931  mov     rcx, [rsp+208h+var_38]
0x140003939  xor     rcx, rsp; StackCookie
0x14000393c  call    __security_check_cookie
0x140003941  add     rsp, 1E8h
0x140003948  pop     rdi
0x140003949  pop     rsi
0x14000394a  pop     rbp
0x14000394b  pop     rbx
0x14000394c  retn
```
