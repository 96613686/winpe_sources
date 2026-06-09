# RegSaveStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180086fa0`
- end: `0x180087065`
- name: `?RegSaveStringValue@@YAKPEAUHKEY__@@PEBG111@Z`
- size: `197`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, wchar_t *Source)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180092628`

## callees

- `0x180086570`
- `0x180086fa0`
- `0x18008aa28`
- `0x18008aad8`
- `0x18008af7c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180086fce`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180086fce`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180087013`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180087013`

## string_xrefs

- `0x180087022`: `RegSetKeyValueW`
- `0x18008704c`: `%s: Failed to set registry value "%s@%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegSaveStringValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        wchar_t *Source)
{
  int v5; // eax
  size_t v10; // rax
  unsigned int v11; // ebx
  LSTATUS v12; // eax
  unsigned __int16 *RegValueName; // rax
  LPCVOID lpData; // [rsp+20h] [rbp-38h]

  v5 = 0;
  if ( Source )
  {
    v10 = wcsnlen(Source, 0x7FFFFFFFu);
    if ( v10 == 0x7FFFFFFF )
    {
      Logger::TraceWarning(L"%s: The string pointed to by pData is too long", L"RegSaveStringValue");
      return 1743;
    }
    v5 = v10 + 1;
  }
  v12 = RegSetKeyValueW(hKey, lpSubKey, a3, 1u, Source, 2 * v5);
  v11 = v12;
  if ( v12 )
  {
    Logger::WriteRegistryFailureEvent(v12, L"RegSetKeyValueW", a4, a3);
    RegValueName = GetRegValueName(a3);
    LODWORD(lpData) = v11;
    Logger::TraceError(
      L"%s: Failed to set registry value \"%s@%s\". Error code: 0x%08x.",
      L"RegSaveStringValue",
      a4,
      RegValueName,
      lpData);
  }
  return v11;
}

```

## disassembly

```asm
0x180086fa0  push    rbx
0x180086fa2  push    rbp
0x180086fa3  push    rsi
0x180086fa4  push    rdi
0x180086fa5  push    r14
0x180086fa7  sub     rsp, 30h
0x180086fab  mov     rbx, [rsp+58h+Source]
0x180086fb3  xor     eax, eax
0x180086fb5  mov     rsi, r9
0x180086fb8  mov     rdi, r8
0x180086fbb  mov     rbp, rdx
0x180086fbe  mov     r14, rcx
0x180086fc1  test    rbx, rbx
0x180086fc4  jz      short loc_180086FF9
0x180086fc6  mov     edx, 7FFFFFFFh; MaxCount
0x180086fcb  mov     rcx, rbx; Source
0x180086fce  call    cs:__imp_wcsnlen
0x180086fd4  cmp     rax, 7FFFFFFFh
0x180086fda  jnz     short loc_180086FF6
0x180086fdc  lea     rdx, aRegsavestringv; "RegSaveStringValue"
0x180086fe3  lea     rcx, aSTheStringPoin; "%s: The string pointed to by pData is t"...
0x180086fea  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086fef  mov     ebx, 6CFh
0x180086ff4  jmp     short loc_180087058
0x180086ff6  inc     rax
0x180086ff9  add     eax, eax
0x180086ffb  mov     r9d, 1; dwType
0x180087001  mov     [rsp+58h+cbData], eax; cbData
0x180087005  mov     r8, rdi; lpValueName
0x180087008  mov     rdx, rbp; lpSubKey
0x18008700b  mov     [rsp+58h+lpData], rbx; lpData
0x180087010  mov     rcx, r14; hKey
0x180087013  call    cs:__imp_RegSetKeyValueW
0x180087019  mov     ebx, eax
0x18008701b  test    eax, eax
0x18008701d  jz      short loc_180087058
0x18008701f  mov     r9, rdi; unsigned __int16 *
0x180087022  lea     rdx, aRegsetkeyvalue; "RegSetKeyValueW"
0x180087029  mov     r8, rsi; unsigned __int16 *
0x18008702c  mov     ecx, eax; unsigned int
0x18008702e  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180087033  mov     rcx, rdi; unsigned __int16 *
0x180087036  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18008703b  mov     r9, rax
0x18008703e  mov     dword ptr [rsp+58h+lpData], ebx
0x180087042  mov     r8, rsi
0x180087045  lea     rdx, aRegsavestringv; "RegSaveStringValue"
0x18008704c  lea     rcx, aSFailedToSetRe; "%s: Failed to set registry value \"%s@%"...
0x180087053  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087058  mov     eax, ebx
0x18008705a  add     rsp, 30h
0x18008705e  pop     r14
0x180087060  pop     rdi
0x180087061  pop     rsi
0x180087062  pop     rbp
0x180087063  pop     rbx
0x180087064  retn
```
