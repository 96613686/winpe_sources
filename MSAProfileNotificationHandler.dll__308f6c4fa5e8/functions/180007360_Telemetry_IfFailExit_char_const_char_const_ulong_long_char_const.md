# Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)

- ea: `0x180007360`
- end: `0x180007511`
- name: `?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z`
- size: `433`
- prototype: `void __fastcall(const char *, const char *, char, int, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ae0`

## callees

- `0x180007360`
- `0x180007518`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800073cc`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180007403`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18000743a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180007471`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800074a1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800074d1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800073cc`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180007403`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18000743a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180007471`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800074a1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800074d1`

## string_xrefs

- `0x1800073c2`: `onecoreuap\ds\ext\live\identity\profilenotificationhandler\dll\profilenotificationimplementation.cpp`
- `0x1800073f4`: `onecoreuap\ds\ext\live\identity\profilenotificationhandler\dll\profilenotificationimplementation.cpp`
- `0x18000742b`: `onecoreuap\ds\ext\live\identity\profilenotificationhandler\dll\profilenotificationimplementation.cpp`
- `0x180007462`: `onecoreuap\ds\ext\live\identity\profilenotificationhandler\dll\profilenotificationimplementation.cpp`
- `0x180007492`: `onecoreuap\ds\ext\live\identity\profilenotificationhandler\dll\profilenotificationimplementation.cpp`
- `0x1800074c2`: `onecoreuap\ds\ext\live\identity\profilenotificationhandler\dll\profilenotificationimplementation.cpp`

## pseudocode

```c
void __fastcall Telemetry::IfFailExit(const char *a1, const char *a2, char a3, int a4, const char *a5)
{
  char v5; // di
  const char *v7; // rbx
  char *v8; // rax
  int v9; // ecx
  int v10; // r9d
  __int64 *v11; // rdx
  char *v12; // rax
  char *v13; // rax
  char *v14; // rax
  char *v15; // rax
  char *v16; // rax

  if ( a4 < 0 )
  {
    v5 = a4;
    switch ( dword_1800134CC )
    {
      case 4:
        if ( byte_1800134C3 >= 0 )
          return;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp";
        v16 = strrchr(
                "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp",
                92);
        if ( v16 )
          LODWORD(v7) = (_DWORD)v16 + 1;
        v11 = WlidSvc_TraceFailure;
        goto LABEL_32;
      case 5:
        if ( (byte_1800134C5 & 0x10) == 0 )
          return;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp";
        v15 = strrchr(
                "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp",
                92);
        if ( v15 )
          LODWORD(v7) = (_DWORD)v15 + 1;
        v11 = WlidModern_TraceFailure;
        goto LABEL_32;
      case 6:
        if ( (byte_1800134C7 & 1) == 0 )
          return;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp";
        v14 = strrchr(
                "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp",
                92);
        if ( v14 )
          LODWORD(v7) = (_DWORD)v14 + 1;
        v11 = WlidCli_TraceFailure;
        goto LABEL_32;
      case 7:
        if ( (byte_1800134C8 & 1) == 0 )
          return;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp";
        v13 = strrchr(
                "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp",
                92);
        if ( v13 )
          LODWORD(v7) = (_DWORD)v13 + 1;
        v11 = WlidProv_TraceFailure;
        goto LABEL_32;
      case 8:
        if ( (byte_1800134C9 & 2) == 0 )
          return;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp";
        v12 = strrchr(
                "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp",
                92);
        if ( v12 )
          LODWORD(v7) = (_DWORD)v12 + 1;
        v11 = WlidBho_TraceFailure;
        goto LABEL_32;
    }
    if ( dword_1800134CC == 9 && (byte_1800134CA & 2) != 0 )
    {
      v7 = "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp";
      v8 = strrchr(
             "onecoreuap\\ds\\ext\\live\\identity\\profilenotificationhandler\\dll\\profilenotificationimplementation.cpp",
             92);
      if ( v8 )
        LODWORD(v7) = (_DWORD)v8 + 1;
      v11 = TokenProvider_TraceFailure;
LABEL_32:
      McTemplateU0ssqsd_EventWriteTransfer(v9, (_DWORD)v11, (_DWORD)v7, v10, a3, (__int64)a5, v5);
    }
  }
}

```

## disassembly

```asm
0x180007360  test    r9d, r9d
0x180007363  jns     locret_180007510
0x180007369  mov     [rsp+arg_0], rbx
0x18000736e  mov     [rsp+arg_8], rsi
0x180007373  push    rdi
0x180007374  sub     rsp, 40h
0x180007378  mov     ecx, cs:dword_1800134CC
0x18000737e  mov     edi, r9d
0x180007381  mov     esi, r8d
0x180007384  sub     ecx, 4
0x180007387  jz      loc_1800074B9
0x18000738d  sub     ecx, 1
0x180007390  jz      loc_180007489
0x180007396  sub     ecx, 1
0x180007399  jz      loc_180007455
0x18000739f  sub     ecx, 1
0x1800073a2  jz      short loc_18000741E
0x1800073a4  sub     ecx, 1
0x1800073a7  jz      short loc_1800073E7
0x1800073a9  cmp     ecx, 1
0x1800073ac  jnz     loc_180007501
0x1800073b2  test    cs:byte_1800134CA, 2
0x1800073b9  jz      loc_180007501
0x1800073bf  lea     edx, [rcx+5Bh]; Ch
0x1800073c2  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\pr"...
0x1800073c9  mov     rcx, rbx; Str
0x1800073cc  call    cs:__imp_strrchr
0x1800073d2  test    rax, rax
0x1800073d5  jz      short loc_1800073DB
0x1800073d7  lea     rbx, [rax+1]
0x1800073db  lea     rdx, TokenProvider_TraceFailure
0x1800073e2  jmp     loc_1800074E7
0x1800073e7  test    cs:byte_1800134C9, 2
0x1800073ee  jz      loc_180007501
0x1800073f4  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\pr"...
0x1800073fb  mov     edx, 5Ch ; '\'; Ch
0x180007400  mov     rcx, rbx; Str
0x180007403  call    cs:__imp_strrchr
0x180007409  test    rax, rax
0x18000740c  jz      short loc_180007412
0x18000740e  lea     rbx, [rax+1]
0x180007412  lea     rdx, WlidBho_TraceFailure
0x180007419  jmp     loc_1800074E7
0x18000741e  test    cs:byte_1800134C8, 1
0x180007425  jz      loc_180007501
0x18000742b  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\pr"...
0x180007432  mov     edx, 5Ch ; '\'; Ch
0x180007437  mov     rcx, rbx; Str
0x18000743a  call    cs:__imp_strrchr
0x180007440  test    rax, rax
0x180007443  jz      short loc_180007449
0x180007445  lea     rbx, [rax+1]
0x180007449  lea     rdx, WlidProv_TraceFailure
0x180007450  jmp     loc_1800074E7
0x180007455  test    cs:byte_1800134C7, 1
0x18000745c  jz      loc_180007501
0x180007462  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\pr"...
0x180007469  mov     edx, 5Ch ; '\'; Ch
0x18000746e  mov     rcx, rbx; Str
0x180007471  call    cs:__imp_strrchr
0x180007477  test    rax, rax
0x18000747a  jz      short loc_180007480
0x18000747c  lea     rbx, [rax+1]
0x180007480  lea     rdx, WlidCli_TraceFailure
0x180007487  jmp     short loc_1800074E7
0x180007489  test    cs:byte_1800134C5, 10h
0x180007490  jz      short loc_180007501
0x180007492  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\pr"...
0x180007499  mov     edx, 5Ch ; '\'; Ch
0x18000749e  mov     rcx, rbx; Str
0x1800074a1  call    cs:__imp_strrchr
0x1800074a7  test    rax, rax
0x1800074aa  jz      short loc_1800074B0
0x1800074ac  lea     rbx, [rax+1]
0x1800074b0  lea     rdx, WlidModern_TraceFailure
0x1800074b7  jmp     short loc_1800074E7
0x1800074b9  cmp     cs:byte_1800134C3, 0
0x1800074c0  jge     short loc_180007501
0x1800074c2  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\pr"...
0x1800074c9  mov     edx, 5Ch ; '\'; Ch
0x1800074ce  mov     rcx, rbx; Str
0x1800074d1  call    cs:__imp_strrchr
0x1800074d7  test    rax, rax
0x1800074da  jz      short loc_1800074E0
0x1800074dc  lea     rbx, [rax+1]
0x1800074e0  lea     rdx, WlidSvc_TraceFailure
0x1800074e7  mov     rax, [rsp+48h+arg_20]
0x1800074ec  mov     r8, rbx
0x1800074ef  mov     [rsp+48h+var_18], edi
0x1800074f3  mov     [rsp+48h+var_20], rax
0x1800074f8  mov     [rsp+48h+var_28], esi
0x1800074fc  call    McTemplateU0ssqsd_EventWriteTransfer
0x180007501  mov     rbx, [rsp+48h+arg_0]
0x180007506  mov     rsi, [rsp+48h+arg_8]
0x18000750b  add     rsp, 40h
0x18000750f  pop     rdi
0x180007510  retn
```
