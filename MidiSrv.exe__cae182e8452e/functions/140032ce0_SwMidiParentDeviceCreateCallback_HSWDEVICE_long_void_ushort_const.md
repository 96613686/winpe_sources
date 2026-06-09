# SwMidiParentDeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x140032ce0`
- end: `0x140032dbb`
- name: `?SwMidiParentDeviceCreateCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `219`
- prototype: `void(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000c55c`
- `0x14000c598`
- `0x14001440c`
- `0x140032ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140032d89`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140032d89`

## string_xrefs

- `0x140032d1f`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
void __fastcall SwMidiParentDeviceCreateCallback(
        struct HSWDEVICE__ *a1,
        int a2,
        HANDLE *a3,
        const unsigned __int16 *a4)
{
  _DWORD *v5; // rax
  unsigned __int64 v6; // r8
  __int64 v7; // r8
  const char *v8; // r9
  _OWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 )
  {
    *(_DWORD *)*a3 = 3;
    *((_DWORD *)*a3 + 16) = a2;
    if ( a2 >= 0 )
    {
      v5 = *a3;
      v6 = -1;
      v9[0] = 0;
      *v5 = 2;
      v9[1] = 0;
      do
        ++v6;
      while ( a4[v6] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v9, a4, v6);
      std::wstring::operator=((char **)*a3 + 4, (__int64)v9);
      std::wstring::~wstring((char **)v9);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x216,
        (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)a2);
    }
    if ( !SetEvent(a3[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
  }
}

```

## disassembly

```asm
0x140032ce0  test    r8, r8
0x140032ce3  jz      locret_140032DAA
0x140032ce9  mov     [rsp+arg_0], rbx
0x140032cee  push    rdi
0x140032cef  sub     rsp, 50h
0x140032cf3  mov     rax, cs:__security_cookie
0x140032cfa  xor     rax, rsp
0x140032cfd  mov     [rsp+58h+var_18], rax
0x140032d02  mov     rax, [r8]
0x140032d05  xor     edi, edi
0x140032d07  mov     rbx, r8
0x140032d0a  mov     dword ptr [rax], 3
0x140032d10  mov     rax, [r8]
0x140032d13  mov     [rax+40h], edx
0x140032d16  test    edx, edx
0x140032d18  jns     short loc_140032D35
0x140032d1a  mov     rcx, [rsp+58h]; this
0x140032d1f  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140032d26  mov     r9d, edx; char *
0x140032d29  mov     edx, 216h; void *
0x140032d2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140032d33  jmp     short loc_140032D85
0x140032d35  mov     rax, [r8]
0x140032d38  xorps   xmm0, xmm0
0x140032d3b  xorps   xmm1, xmm1
0x140032d3e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140032d42  movups  [rsp+58h+var_38], xmm0
0x140032d47  mov     dword ptr [rax], 2
0x140032d4d  movdqu  [rsp+58h+var_28], xmm1
0x140032d53  inc     r8
0x140032d56  cmp     [r9+r8*2], di
0x140032d5b  jnz     short loc_140032D53
0x140032d5d  mov     rdx, r9
0x140032d60  lea     rcx, [rsp+58h+var_38]
0x140032d65  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140032d6a  mov     rcx, [rbx]
0x140032d6d  lea     rdx, [rsp+58h+var_38]
0x140032d72  add     rcx, 20h ; ' '
0x140032d76  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140032d7b  lea     rcx, [rsp+58h+var_38]; void *
0x140032d80  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140032d85  mov     rcx, [rbx+8]; hEvent
0x140032d89  call    cs:__imp_SetEvent
0x140032d8f  test    eax, eax
0x140032d91  jz      short loc_140032DAB
0x140032d93  mov     rcx, [rsp+58h+var_18]
0x140032d98  xor     rcx, rsp; StackCookie
0x140032d9b  call    __security_check_cookie
0x140032da0  mov     rbx, [rsp+58h+arg_0]
0x140032da5  add     rsp, 50h
0x140032da9  pop     rdi
0x140032daa  retn
0x140032dab  mov     rcx, [rsp+58h]; this
0x140032db0  mov     edx, 0A01h; void *
0x140032db5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
