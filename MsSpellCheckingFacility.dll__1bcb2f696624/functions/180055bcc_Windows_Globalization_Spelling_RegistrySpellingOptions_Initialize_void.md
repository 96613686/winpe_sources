# Windows::Globalization::Spelling::RegistrySpellingOptions::Initialize(void)

- ea: `0x180055bcc`
- end: `0x180055c88`
- name: `?Initialize@RegistrySpellingOptions@Spelling@Globalization@Windows@@AEAAXXZ`
- size: `188`
- prototype: `void __fastcall(Windows::Globalization::Spelling::RegistrySpellingOptions *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053170`

## callees

- `0x180055bcc`
- `0x18005b5bc`
- `0x180075b80`
- `0x180087394`
- `0x18008b4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055c35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055c35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180055c15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180055c15`

## pseudocode

```c
void __fastcall Windows::Globalization::Spelling::RegistrySpellingOptions::Initialize(
        Windows::Globalization::Spelling::RegistrySpellingOptions *this)
{
  HKEY *v1; // rdi
  int Key; // eax
  Windows::Globalization::Spelling::RegistrySpellingOptions *v4; // rcx
  bool v5; // sf
  HANDLE EventW; // rax

  v1 = (HKEY *)((char *)this + 40);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Spelling", 0, 0, 0, 0x10u, 0, (PHKEY)this + 5, 0);
  v5 = Key < 0;
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key | 0x80070000;
    v5 = Key < 0;
  }
  if ( v5
    || (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 6) = EventW) == 0)
    && (Key = ResultFromKnownLastError(), Key < 0)
    || (Key = Windows::Globalization::Spelling::RegistrySpellingOptions::AssociateEventToRegistryChange(
                v4,
                *v1,
                *((void **)this + 6)),
        Key < 0) )
  {
    if ( (Microsoft_Windows_Spell_CheckingEnableBits & 4) != 0 )
      McTemplateU0d_EventWriteTransfer(v4, OptionsWatchingFailed, (unsigned int)Key);
    Windows::Globalization::Spelling::RegistrySpellingOptions::ReleaseEventHandle(this);
  }
}

```

## disassembly

```asm
0x180055bcc  mov     rax, rsp
0x180055bcf  mov     [rax+8], rbx
0x180055bd3  push    rdi
0x180055bd4  sub     rsp, 50h
0x180055bd8  mov     qword ptr [rax-18h], 0
0x180055be0  lea     rdi, [rcx+28h]
0x180055be4  mov     [rax-20h], rdi
0x180055be8  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Spelling"
0x180055bef  mov     qword ptr [rax-28h], 0
0x180055bf7  mov     rbx, rcx
0x180055bfa  mov     dword ptr [rax-30h], 10h
0x180055c01  xor     r9d, r9d; lpClass
0x180055c04  xor     r8d, r8d; Reserved
0x180055c07  mov     dword ptr [rax-38h], 0
0x180055c0e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180055c15  call    cs:__imp_RegCreateKeyExW
0x180055c1b  test    eax, eax
0x180055c1d  jle     short loc_180055C29
0x180055c1f  movzx   eax, ax
0x180055c22  or      eax, 80070000h
0x180055c27  test    eax, eax
0x180055c29  js      short loc_180055C5D
0x180055c2b  xor     r9d, r9d; lpName
0x180055c2e  xor     r8d, r8d; bInitialState
0x180055c31  xor     edx, edx; bManualReset
0x180055c33  xor     ecx, ecx; lpEventAttributes
0x180055c35  call    cs:__imp_CreateEventW
0x180055c3b  mov     [rbx+30h], rax
0x180055c3f  test    rax, rax
0x180055c42  jnz     short loc_180055C4D
0x180055c44  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055c49  test    eax, eax
0x180055c4b  js      short loc_180055C5D
0x180055c4d  mov     r8, [rbx+30h]; void *
0x180055c51  mov     rdx, [rdi]; HKEY
0x180055c54  call    ?AssociateEventToRegistryChange@RegistrySpellingOptions@Spelling@Globalization@Windows@@AEAAJPEAUHKEY__@@PEAX@Z; Windows::Globalization::Spelling::RegistrySpellingOptions::AssociateEventToRegistryChange(HKEY__ *,void *)
0x180055c59  test    eax, eax
0x180055c5b  jns     short loc_180055C7D
0x180055c5d  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 4
0x180055c64  jz      short loc_180055C75
0x180055c66  mov     r8d, eax
0x180055c69  lea     rdx, OptionsWatchingFailed
0x180055c70  call    McTemplateU0d_EventWriteTransfer
0x180055c75  mov     rcx, rbx; this
0x180055c78  call    ?ReleaseEventHandle@RegistrySpellingOptions@Spelling@Globalization@Windows@@AEAAXXZ; Windows::Globalization::Spelling::RegistrySpellingOptions::ReleaseEventHandle(void)
0x180055c7d  mov     rbx, [rsp+58h+arg_0]
0x180055c82  add     rsp, 50h
0x180055c86  pop     rdi
0x180055c87  retn
```
