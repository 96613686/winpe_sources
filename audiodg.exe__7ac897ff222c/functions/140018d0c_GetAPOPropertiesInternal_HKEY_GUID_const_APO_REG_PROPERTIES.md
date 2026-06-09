# GetAPOPropertiesInternal(HKEY__ *,_GUID const &,APO_REG_PROPERTIES *)

- ea: `0x140018d0c`
- end: `0x140018e5f`
- name: `?GetAPOPropertiesInternal@@YAJPEAUHKEY__@@AEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(HKEY hKey, const struct _GUID *, struct APO_REG_PROPERTIES *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400476e8`
- `0x14004de70`

## callees

- `0x140018d0c`
- `0x140018e68`
- `0x140018ef0`
- `0x14005d0e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018e3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018e3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018e1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018e1b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140018d4a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140018d4a`

## pseudocode

```c
__int64 __fastcall GetAPOPropertiesInternal(HKEY hKey, const struct _GUID *a2, struct APO_REG_PROPERTIES *a3)
{
  __int64 v6; // rdx
  OLECHAR *v7; // rax
  signed int APOProperties; // ebx
  HKEY hKeya; // [rsp+30h] [rbp-138h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-128h] BYREF
  WCHAR SubKey[80]; // [rsp+90h] [rbp-D8h] BYREF

  if ( StringFromGUID2(a2, sz, 39) <= 0 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v6 = 39;
    v7 = sz;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    APOProperties = v6 == 0 ? 0x80070057 : 0;
    if ( v6 )
    {
      if ( ((39 - v6) & -(__int64)(v6 != 0)) == 0x26 )
      {
        APOProperties = StringCchPrintfW(SubKey, 0x4Bu, L"%s\\%s", L"AudioEngine\\AudioProcessingObjects", sz);
        if ( APOProperties >= 0 )
        {
          hKeya = 0;
          if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya) )
          {
            return (unsigned int)-2005139398;
          }
          else
          {
            APOProperties = InnerGetAPOProperties(hKeya, a2, a3);
            RegCloseKey(hKeya);
          }
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  return (unsigned int)APOProperties;
}

```

## disassembly

```asm
0x140018d0c  mov     [rsp+arg_18], rbx
0x140018d11  push    rbp
0x140018d12  push    rsi
0x140018d13  push    rdi
0x140018d14  push    r14
0x140018d16  push    r15
0x140018d18  sub     rsp, 140h
0x140018d1f  mov     rax, cs:__security_cookie
0x140018d26  xor     rax, rsp
0x140018d29  mov     [rsp+168h+var_38], rax
0x140018d31  mov     rsi, rdx
0x140018d34  mov     rbp, r8
0x140018d37  mov     r14, rcx
0x140018d3a  lea     rdx, [rsp+168h+sz]; lpsz
0x140018d3f  mov     edi, 27h ; '''
0x140018d44  mov     rcx, rsi; rguid
0x140018d47  mov     r8d, edi; cchMax
0x140018d4a  call    cs:__imp_StringFromGUID2
0x140018d50  xor     r15d, r15d
0x140018d53  test    eax, eax
0x140018d55  jle     loc_140018E44
0x140018d5b  mov     edx, edi
0x140018d5d  lea     rax, [rsp+168h+sz]
0x140018d62  cmp     [rax], r15w
0x140018d66  jz      short loc_140018D72
0x140018d68  add     rax, 2
0x140018d6c  sub     rdx, 1
0x140018d70  jnz     short loc_140018D62
0x140018d72  mov     rax, rdx
0x140018d75  mov     ebx, 80070057h
0x140018d7a  neg     rax
0x140018d7d  mov     rax, rdx
0x140018d80  sbb     ecx, ecx
0x140018d82  sub     rdi, rdx
0x140018d85  not     ecx
0x140018d87  and     ebx, ecx
0x140018d89  neg     rax
0x140018d8c  sbb     rcx, rcx
0x140018d8f  and     rcx, rdi
0x140018d92  test    rdx, rdx
0x140018d95  jz      short loc_140018DCF
0x140018d97  cmp     rcx, 26h ; '&'
0x140018d9b  jnz     loc_140018E4B
0x140018da1  lea     rax, [rsp+168h+sz]
0x140018da6  lea     edx, [rcx+25h]; unsigned __int64
0x140018da9  mov     [rsp+168h+phkResult], rax
0x140018dae  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x140018db6  lea     r9, aAudioengineAud; "AudioEngine\\AudioProcessingObjects"
0x140018dbd  lea     r8, aSS; "%s\\%s"
0x140018dc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018dc9  mov     ebx, eax
0x140018dcb  test    eax, eax
0x140018dcd  jns     short loc_140018DF8
0x140018dcf  mov     eax, ebx
0x140018dd1  mov     rcx, [rsp+168h+var_38]
0x140018dd9  xor     rcx, rsp; StackCookie
0x140018ddc  call    __security_check_cookie
0x140018de1  mov     rbx, [rsp+168h+arg_18]
0x140018de9  add     rsp, 140h
0x140018df0  pop     r15
0x140018df2  pop     r14
0x140018df4  pop     rdi
0x140018df5  pop     rsi
0x140018df6  pop     rbp
0x140018df7  retn
0x140018df8  lea     rax, [rsp+168h+hKey]
0x140018dfd  mov     [rsp+168h+hKey], r15
0x140018e02  mov     r9d, 20019h; samDesired
0x140018e08  mov     [rsp+168h+phkResult], rax; phkResult
0x140018e0d  xor     r8d, r8d; ulOptions
0x140018e10  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x140018e18  mov     rcx, r14; hKey
0x140018e1b  call    cs:__imp_RegOpenKeyExW
0x140018e21  test    eax, eax
0x140018e23  jnz     short loc_140018E55
0x140018e25  mov     rcx, [rsp+168h+hKey]; hKey
0x140018e2a  mov     r8, rbp; struct APO_REG_PROPERTIES *
0x140018e2d  mov     rdx, rsi; struct _GUID *
0x140018e30  call    ?InnerGetAPOProperties@@YAJPEAUHKEY__@@AEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z; InnerGetAPOProperties(HKEY__ *,_GUID const &,APO_REG_PROPERTIES *)
0x140018e35  mov     rcx, [rsp+168h+hKey]; hKey
0x140018e3a  mov     ebx, eax
0x140018e3c  call    cs:__imp_RegCloseKey
0x140018e42  jmp     short loc_140018DCF
0x140018e44  mov     ebx, 80070057h
0x140018e49  jmp     short loc_140018DCF
0x140018e4b  mov     ebx, 8000FFFFh
0x140018e50  jmp     loc_140018DCF
0x140018e55  mov     ebx, 887C003Ah
0x140018e5a  jmp     loc_140018DCF
```
