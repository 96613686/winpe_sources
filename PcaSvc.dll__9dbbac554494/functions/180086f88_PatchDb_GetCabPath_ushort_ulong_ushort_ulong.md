# PatchDb_GetCabPath(ushort *,ulong,ushort *,ulong)

- ea: `0x180086f88`
- end: `0x180087101`
- name: `?PatchDb_GetCabPath@@YAKPEAGK0K@Z`
- size: `377`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004248c`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x180086f88`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18008700c`
- `ntdll!RtlStringFromGUID` at `0x18008700c`
- `ntdll!RtlGetNtSystemRoot` at `0x18008702e`
- `ntdll!RtlGetNtSystemRoot` at `0x180087080`
- `ntdll!RtlGetNtSystemRoot` at `0x18008702e`
- `ntdll!RtlGetNtSystemRoot` at `0x180087080`
- `ntdll!RtlFreeUnicodeString` at `0x1800870e1`
- `ntdll!RtlFreeUnicodeString` at `0x1800870e1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180086fbc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180086fbc`

## string_xrefs

- `0x180086fec`: `PatchDb_GetCabPath`
- `0x18008706e`: `Failed to get cab file path %d`
- `0x1800870c0`: `Failed to get cab dir path %d`
- `0x18008701b`: `Failed to generate directory name. %d`
- `0x180086fdf`: `Failed to generate directory guid. %x`
- `0x180087086`: `%s\temp\sdb%s`
- `0x180087034`: `%s\temp\sdb%s.cab`

## pseudocode

```c
__int64 __fastcall PatchDb_GetCabPath(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 NtSystemRoot; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  HRESULT v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+20h] [rbp-48h]
  __int64 v15; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-38h] BYREF
  GUID pguid; // [rsp+40h] [rbp-28h] BYREF

  pguid = 0;
  GuidString = 0;
  v5 = CoCreateGuid(&pguid);
  if ( v5 >= 0 )
  {
    if ( RtlStringFromGUID(&pguid, &GuidString) >= 0 )
    {
      NtSystemRoot = RtlGetNtSystemRoot();
      v8 = StringCchPrintfW(a1, 0x104u, L"%s\\temp\\sdb%s.cab", NtSystemRoot, GuidString.Buffer);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v9 = RtlGetNtSystemRoot();
        v10 = StringCchPrintfW(a3, 0x104u, L"%s\\temp\\sdb%s", v9, GuidString.Buffer);
        v6 = v10;
        if ( v10 >= 0 )
        {
          v6 = 0;
        }
        else
        {
          if ( (v10 & 0x1FFF0000) == 0x70000 )
            v6 = (unsigned __int16)v10;
          LODWORD(v15) = v6;
          AslLogCallPrintf(
            1,
            (unsigned int)"PatchDb_GetCabPath",
            1085,
            (unsigned int)"Failed to get cab dir path %d",
            v15);
        }
      }
      else
      {
        if ( (v8 & 0x1FFF0000) == 0x70000 )
          v6 = (unsigned __int16)v8;
        LODWORD(v14) = v6;
        AslLogCallPrintf(
          1,
          (unsigned int)"PatchDb_GetCabPath",
          1073,
          (unsigned int)"Failed to get cab file path %d",
          v14);
      }
    }
    else
    {
      v6 = 8;
      v13 = 8;
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_GetCabPath",
        1061,
        (unsigned int)"Failed to generate directory name. %d",
        v13);
    }
  }
  else
  {
    v6 = (unsigned __int16)v5;
    if ( (v5 & 0x1FFF0000) != 0x70000 )
      v6 = v5;
    v12 = v5;
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_GetCabPath",
      1055,
      (unsigned int)"Failed to generate directory guid. %x",
      v12);
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return v6;
}

```

## disassembly

```asm
0x180086f88  mov     [rsp+arg_8], rbx
0x180086f8d  push    rdi
0x180086f8e  sub     rsp, 60h
0x180086f92  mov     rax, cs:__security_cookie
0x180086f99  xor     rax, rsp
0x180086f9c  mov     [rsp+68h+var_18], rax
0x180086fa1  mov     rbx, rcx
0x180086fa4  xorps   xmm0, xmm0
0x180086fa7  xorps   xmm1, xmm1
0x180086faa  lea     rcx, [rsp+68h+pguid]; pguid
0x180086faf  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x180086fb4  mov     rdi, r8
0x180086fb7  movups  xmmword ptr [rsp+68h+GuidString.Length], xmm1
0x180086fbc  call    cs:__imp_CoCreateGuid
0x180086fc2  test    eax, eax
0x180086fc4  jns     short loc_180087002
0x180086fc6  mov     ecx, eax
0x180086fc8  movzx   ebx, ax
0x180086fcb  and     ecx, 1FFF0000h
0x180086fd1  cmp     ecx, 70000h
0x180086fd7  jz      short loc_180086FDB
0x180086fd9  mov     ebx, eax
0x180086fdb  mov     [rsp+68h+var_48], eax
0x180086fdf  lea     r9, aFailedToGenera_1; "Failed to generate directory guid. %x"
0x180086fe6  mov     r8d, 41Fh
0x180086fec  lea     rdx, aPatchdbGetcabp; "PatchDb_GetCabPath"
0x180086ff3  mov     ecx, 1
0x180086ff8  call    AslLogCallPrintf
0x180086ffd  jmp     loc_1800870D4
0x180087002  lea     rdx, [rsp+68h+GuidString]; GuidString
0x180087007  lea     rcx, [rsp+68h+pguid]; Guid
0x18008700c  call    cs:__imp_RtlStringFromGUID
0x180087012  test    eax, eax
0x180087014  jns     short loc_18008702E
0x180087016  mov     ebx, 8
0x18008701b  lea     r9, aFailedToGenera_0; "Failed to generate directory name. %d"
0x180087022  mov     [rsp+68h+var_48], ebx
0x180087026  mov     r8d, 425h
0x18008702c  jmp     short loc_180086FEC
0x18008702e  call    cs:__imp_RtlGetNtSystemRoot
0x180087034  lea     r8, aSTempSdbSCab; "%s\\temp\\sdb%s.cab"
0x18008703b  mov     edx, 104h; unsigned __int64
0x180087040  mov     r9, rax
0x180087043  mov     rcx, rbx; unsigned __int16 *
0x180087046  mov     rax, [rsp+68h+GuidString.Buffer]
0x18008704b  mov     qword ptr [rsp+68h+var_48], rax
0x180087050  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180087055  mov     ebx, eax
0x180087057  test    eax, eax
0x180087059  jns     short loc_180087080
0x18008705b  and     eax, 1FFF0000h
0x180087060  cmp     eax, 70000h
0x180087065  jnz     short loc_18008706A
0x180087067  movzx   ebx, bx
0x18008706a  mov     [rsp+68h+var_48], ebx
0x18008706e  lea     r9, aFailedToGetCab; "Failed to get cab file path %d"
0x180087075  mov     r8d, 431h
0x18008707b  jmp     loc_180086FEC
0x180087080  call    cs:__imp_RtlGetNtSystemRoot
0x180087086  lea     r8, aSTempSdbS; "%s\\temp\\sdb%s"
0x18008708d  mov     edx, 104h; unsigned __int64
0x180087092  mov     r9, rax
0x180087095  mov     rcx, rdi; unsigned __int16 *
0x180087098  mov     rax, [rsp+68h+GuidString.Buffer]
0x18008709d  mov     qword ptr [rsp+68h+var_48], rax
0x1800870a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800870a7  mov     ebx, eax
0x1800870a9  test    eax, eax
0x1800870ab  jns     short loc_1800870D2
0x1800870ad  and     eax, 1FFF0000h
0x1800870b2  cmp     eax, 70000h
0x1800870b7  jnz     short loc_1800870BC
0x1800870b9  movzx   ebx, bx
0x1800870bc  mov     [rsp+68h+var_48], ebx
0x1800870c0  lea     r9, aFailedToGetCab_0; "Failed to get cab dir path %d"
0x1800870c7  mov     r8d, 43Dh
0x1800870cd  jmp     loc_180086FEC
0x1800870d2  xor     ebx, ebx
0x1800870d4  cmp     [rsp+68h+GuidString.Buffer], 0
0x1800870da  jz      short loc_1800870E7
0x1800870dc  lea     rcx, [rsp+68h+GuidString]; UnicodeString
0x1800870e1  call    cs:__imp_RtlFreeUnicodeString
0x1800870e7  mov     eax, ebx
0x1800870e9  mov     rcx, [rsp+68h+var_18]
0x1800870ee  xor     rcx, rsp; StackCookie
0x1800870f1  call    __security_check_cookie
0x1800870f6  mov     rbx, [rsp+68h+arg_8]
0x1800870fb  add     rsp, 60h
0x1800870ff  pop     rdi
0x180087100  retn
```
