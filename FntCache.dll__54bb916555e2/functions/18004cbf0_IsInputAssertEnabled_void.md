# IsInputAssertEnabled(void)

- ea: `0x18004cbf0`
- end: `0x18004cc98`
- name: `?IsInputAssertEnabled@@YA_NXZ`
- size: `168`
- prototype: `bool(void)`
- caller_count: `87`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005950`
- `0x18000c13c`
- `0x18000c8c8`
- `0x18000ce18`
- `0x18000d060`
- `0x18000d268`
- `0x1800100d0`
- `0x180013b0c`
- `0x180017430`
- `0x180017a50`
- `0x18001bab8`
- `0x18001ccb8`
- `0x18001de08`
- `0x18001e650`
- `0x18001f5ac`
- `0x18001f628`
- `0x18001f7d4`
- `0x18002000c`
- `0x1800206a0`
- `0x18002cf80`
- `0x18002d208`
- `0x18002d2d4`
- `0x180030ce0`
- `0x18003c17c`
- `0x180042ab8`
- `0x1800441e8`
- `0x180044344`
- `0x1800446d4`
- `0x1800447c4`
- `0x1800448b4`
- `0x180045700`
- `0x1800464e0`
- `0x180046784`
- `0x180046fb8`
- `0x1800470a8`
- `0x1800474e0`
- `0x1800476c0`
- `0x18004778c`
- `0x180047910`
- `0x180047ba0`
- `0x180047e10`
- `0x180048f24`
- `0x18004a240`
- `0x18004ab20`
- `0x18004b170`
- `0x18004ba4c`
- `0x18004c1c0`
- `0x18004c6a8`
- `0x18004c940`
- `0x18004d7c4`

## callees

- `0x18004cbf0`
- `0x18006ab6c`
- `0x1800b886c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cc38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cc38`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool IsInputAssertEnabled(void)
{
  int v0; // eax
  unsigned int v2; // ebx
  bool v3; // al
  signed __int32 v4; // ecx
  int Number; // ebx
  unsigned int v6; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  v0 = g_inputAssertEnabled;
  if ( g_inputAssertEnabled == -1 )
  {
    v2 = 0;
    v6 = 0;
    phkResult = 0;
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &phkResult);
    if ( phkResult )
    {
      Number = GetNumber(phkResult, L"InputAssertEnabled", &v6);
      RegistryKey::Close((RegistryKey *)&phkResult);
      v3 = Number == 0;
      v2 = v6;
    }
    else
    {
      v3 = 0;
    }
    v4 = v3 && v2;
    _InterlockedCompareExchange(&g_inputAssertEnabled, v4, -1);
    v0 = g_inputAssertEnabled;
  }
  return v0 != 0;
}

```

## disassembly

```asm
0x18004cbf0  push    rbx
0x18004cbf2  sub     rsp, 30h
0x18004cbf6  mov     eax, cs:?g_inputAssertEnabled@@3HA; int g_inputAssertEnabled
0x18004cbfc  cmp     eax, 0FFFFFFFFh
0x18004cbff  jz      short loc_18004CC0C
0x18004cc01  test    eax, eax
0x18004cc03  setnz   al
0x18004cc06  add     rsp, 30h
0x18004cc0a  pop     rbx
0x18004cc0b  retn
0x18004cc0c  xor     ebx, ebx
0x18004cc0e  mov     [rsp+38h+arg_0], ebx
0x18004cc12  mov     [rsp+38h+arg_8], rbx
0x18004cc17  lea     rax, [rsp+38h+arg_8]
0x18004cc1c  mov     [rsp+38h+phkResult], rax; phkResult
0x18004cc21  mov     r9d, 20019h; samDesired
0x18004cc27  xor     r8d, r8d; ulOptions
0x18004cc2a  lea     rdx, ?DefaultConfigurationKey@RegistryKey@@2QB_WB; "Software\\Microsoft\\Avalon.Graphics"
0x18004cc31  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cc38  call    cs:__imp_RegOpenKeyExW
0x18004cc3e  mov     rcx, [rsp+38h+arg_8]; HKEY
0x18004cc43  test    rcx, rcx
0x18004cc46  jnz     short loc_18004CC65
0x18004cc48  xor     al, al
0x18004cc4a  test    al, al
0x18004cc4c  jnz     short loc_18004CC8D
0x18004cc4e  xor     ecx, ecx
0x18004cc50  mov     eax, 0FFFFFFFFh
0x18004cc55  lock cmpxchg cs:?g_inputAssertEnabled@@3HA, ecx; int g_inputAssertEnabled
0x18004cc5d  mov     eax, cs:?g_inputAssertEnabled@@3HA; int g_inputAssertEnabled
0x18004cc63  jmp     short loc_18004CC01
0x18004cc65  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18004cc6a  lea     rdx, aInputassertena; "InputAssertEnabled"
0x18004cc71  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x18004cc76  mov     ebx, eax
0x18004cc78  lea     rcx, [rsp+38h+arg_8]; this
0x18004cc7d  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18004cc82  test    ebx, ebx
0x18004cc84  setz    al
0x18004cc87  mov     ebx, [rsp+38h+arg_0]
0x18004cc8b  jmp     short loc_18004CC4A
0x18004cc8d  test    ebx, ebx
0x18004cc8f  jz      short loc_18004CC4E
0x18004cc91  mov     ecx, 1
0x18004cc96  jmp     short loc_18004CC50
```
