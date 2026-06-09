# ViewClusterTmMapping(ushort *)

- ea: `0x18001d978`
- end: `0x18001db75`
- name: `?ViewClusterTmMapping@@YAJPEAG@Z`
- size: `509`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800830c4`

## callees

- `0x1800063b0`
- `0x18001a134`
- `0x18001d978`
- `0x18001ebdc`
- `0x1800846c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da52`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001d9fb`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001d9fb`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001db57`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001db57`
- `CLUSAPI!OpenClusterEx` at `0x18001d9c8`
- `CLUSAPI!OpenClusterEx` at `0x18001d9c8`
- `CLUSAPI!CloseCluster` at `0x18001db60`
- `CLUSAPI!CloseCluster` at `0x18001db60`
- `CLUSAPI!GetClusterKey` at `0x18001da44`
- `CLUSAPI!GetClusterKey` at `0x18001da44`

## string_xrefs

- `0x18001da12`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001da78`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001dae8`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001db2d`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001da06`: `OpenClusterEx failed`
- `0x18001d9f4`: `OpenClusterEx`
- `0x18001d994`: `Service`
- `0x18001d9a0`: `ComplusApp`
- `0x18001d9b1`: `ViewClusterTmMapping (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3289): ViewClusterTmMapping: NULL != pwszMappingName`

## pseudocode

```c
__int64 __fastcall ViewClusterTmMapping(unsigned __int16 *a1)
{
  struct _HCLUSTER *v2; // rax
  struct _HCLUSTER *v3; // rbp
  signed int v4; // eax
  unsigned int v5; // ebx
  HKEY ClusterKey; // r14
  signed int LastError; // eax
  int v8; // esi
  int i; // edi
  int v10; // eax
  __int64 v12; // [rsp+28h] [rbp-70h]
  unsigned __int16 *v13[11]; // [rsp+40h] [rbp-58h]

  v13[0] = L"Exe";
  v13[1] = L"Service";
  v13[2] = L"ComplusApp";
  if ( !a1 )
    DtcInternalErrorW(
      L"ViewClusterTmMapping (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3289): ViewClusterTmMapping: NULL != pwszMappingName");
  v2 = OpenClusterEx(0, 0x2000000u, 0);
  v3 = v2;
  if ( v2 )
  {
    ClusterKey = GetClusterKey(v2, 0x20119u);
    if ( ClusterKey )
    {
      v5 = 0;
      v8 = 0;
      for ( i = 0; i < 3; ++i )
      {
        v10 = DisplayClusterRegKeyInfo(ClusterKey, v13[i], a1);
        v5 = v10;
        if ( v10 >= 0 )
        {
          ++v8;
        }
        else
        {
          if ( v10 != -2147024894 )
          {
            LODWORD(v12) = v10;
            TraceStringInline(
              3,
              1,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              3321,
              L"ViewClusterTmMapping",
              v12,
              L"DisplayClusterRegKeyInfo failed");
            goto LABEL_21;
          }
          v5 = 0;
        }
      }
      if ( !v8 )
      {
        DisplayLocMessageToConsole(0x69u);
        LODWORD(v12) = v5;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          3332,
          L"ViewClusterTmMapping",
          v12,
          L"No such transaction mapping found");
        v5 = -2147467259;
      }
LABEL_21:
      ClusterRegCloseKey(ClusterKey);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v12) = v5;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        3304,
        L"ViewClusterTmMapping",
        v12,
        L"GetClusterKey failed");
    }
    CloseCluster(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    FailedClusterAPIToEventLog(L"OpenClusterEx", v5, L" ");
    LODWORD(v12) = v5;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      3296,
      L"ViewClusterTmMapping",
      v12,
      L"OpenClusterEx failed");
  }
  return v5;
}

```

## disassembly

```asm
0x18001d978  push    rbx
0x18001d97a  push    rbp
0x18001d97b  push    rsi
0x18001d97c  push    rdi
0x18001d97d  push    r14
0x18001d97f  push    r15
0x18001d981  sub     rsp, 68h
0x18001d985  lea     rax, aExe; "Exe"
0x18001d98c  mov     r15, rcx
0x18001d98f  mov     [rsp+98h+var_58], rax
0x18001d994  lea     rax, aService; "Service"
0x18001d99b  mov     [rsp+98h+var_50], rax
0x18001d9a0  lea     rax, aComplusapp; "ComplusApp"
0x18001d9a7  mov     [rsp+98h+var_48], rax
0x18001d9ac  test    rcx, rcx
0x18001d9af  jnz     short loc_18001D9BE
0x18001d9b1  lea     rcx, aViewclustertmm; "ViewClusterTmMapping (com\\complus\\dtc"...
0x18001d9b8  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001d9be  xor     r8d, r8d; GrantedAccess
0x18001d9c1  mov     edx, 2000000h; DesiredAccess
0x18001d9c6  xor     ecx, ecx; lpszClusterName
0x18001d9c8  call    cs:__imp_OpenClusterEx
0x18001d9ce  mov     rbp, rax
0x18001d9d1  test    rax, rax
0x18001d9d4  jnz     short loc_18001DA3C
0x18001d9d6  call    cs:__imp_GetLastError
0x18001d9dc  mov     ebx, eax
0x18001d9de  test    eax, eax
0x18001d9e0  jle     short loc_18001D9EB
0x18001d9e2  movzx   ebx, ax
0x18001d9e5  or      ebx, 80070000h
0x18001d9eb  lea     r8, asc_180127724; " "
0x18001d9f2  mov     edx, ebx
0x18001d9f4  lea     rcx, aOpenclusterex; "OpenClusterEx"
0x18001d9fb  call    cs:__imp_FailedClusterAPIToEventLog
0x18001da01  mov     edx, 1
0x18001da06  lea     rax, aOpenclusterexF; "OpenClusterEx failed"
0x18001da0d  mov     [rsp+98h+var_68], rax
0x18001da12  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001da19  lea     rax, aViewclustertmm_0; "ViewClusterTmMapping"
0x18001da20  mov     dword ptr [rsp+98h+var_70], ebx
0x18001da24  mov     r9d, 0CE0h
0x18001da2a  mov     [rsp+98h+var_78], rax
0x18001da2f  lea     ecx, [rdx+2]
0x18001da32  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001da37  jmp     loc_18001DB66
0x18001da3c  mov     edx, 20119h; samDesired
0x18001da41  mov     rcx, rbp; hCluster
0x18001da44  call    cs:__imp_GetClusterKey
0x18001da4a  mov     r14, rax
0x18001da4d  test    rax, rax
0x18001da50  jnz     short loc_18001DAA2
0x18001da52  call    cs:__imp_GetLastError
0x18001da58  mov     ebx, eax
0x18001da5a  test    eax, eax
0x18001da5c  jle     short loc_18001DA67
0x18001da5e  movzx   ebx, ax
0x18001da61  or      ebx, 80070000h
0x18001da67  mov     edx, 1
0x18001da6c  lea     rax, aGetclusterkeyF; "GetClusterKey failed"
0x18001da73  mov     [rsp+98h+var_68], rax
0x18001da78  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001da7f  lea     rax, aViewclustertmm_0; "ViewClusterTmMapping"
0x18001da86  mov     dword ptr [rsp+98h+var_70], ebx
0x18001da8a  mov     r9d, 0CE8h
0x18001da90  mov     [rsp+98h+var_78], rax
0x18001da95  lea     ecx, [rdx+2]
0x18001da98  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001da9d  jmp     loc_18001DB5D
0x18001daa2  xor     ebx, ebx
0x18001daa4  xor     esi, esi
0x18001daa6  xor     edi, edi
0x18001daa8  cmp     edi, 3
0x18001daab  jge     short loc_18001DB0F
0x18001daad  movsxd  rdx, edi
0x18001dab0  mov     r8, r15; unsigned __int16 *
0x18001dab3  mov     rcx, r14; hKey
0x18001dab6  mov     rdx, [rsp+rdx*8+98h+var_58]; unsigned __int16 *
0x18001dabb  call    ?DisplayClusterRegKeyInfo@@YAJPEAUHKEY__@@PEAG1@Z; DisplayClusterRegKeyInfo(HKEY__ *,ushort *,ushort *)
0x18001dac0  mov     ebx, eax
0x18001dac2  test    eax, eax
0x18001dac4  jns     short loc_18001DAD1
0x18001dac6  cmp     eax, 80070002h
0x18001dacb  jnz     short loc_18001DAD7
0x18001dacd  xor     ebx, ebx
0x18001dacf  jmp     short loc_18001DAD3
0x18001dad1  inc     esi
0x18001dad3  inc     edi
0x18001dad5  jmp     short loc_18001DAA8
0x18001dad7  mov     edx, 1
0x18001dadc  lea     rax, aDisplaycluster_0; "DisplayClusterRegKeyInfo failed"
0x18001dae3  mov     [rsp+98h+var_68], rax
0x18001dae8  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001daef  lea     rax, aViewclustertmm_0; "ViewClusterTmMapping"
0x18001daf6  mov     dword ptr [rsp+98h+var_70], ebx
0x18001dafa  mov     r9d, 0CF9h
0x18001db00  mov     [rsp+98h+var_78], rax
0x18001db05  lea     ecx, [rdx+2]
0x18001db08  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001db0d  jmp     short loc_18001DB54
0x18001db0f  test    esi, esi
0x18001db11  jnz     short loc_18001DB54
0x18001db13  lea     ecx, [rsi+69h]; uID
0x18001db16  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x18001db1b  lea     rax, aNoSuchTransact; "No such transaction mapping found"
0x18001db22  mov     r9d, 0D04h
0x18001db28  mov     [rsp+98h+var_68], rax
0x18001db2d  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001db34  lea     rax, aViewclustertmm_0; "ViewClusterTmMapping"
0x18001db3b  mov     dword ptr [rsp+98h+var_70], ebx
0x18001db3f  lea     edx, [rsi+1]
0x18001db42  mov     [rsp+98h+var_78], rax
0x18001db47  lea     ecx, [rsi+3]
0x18001db4a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001db4f  mov     ebx, 80004005h
0x18001db54  mov     rcx, r14; hKey
0x18001db57  call    cs:__imp_ClusterRegCloseKey
0x18001db5d  mov     rcx, rbp; hCluster
0x18001db60  call    cs:__imp_CloseCluster
0x18001db66  mov     eax, ebx
0x18001db68  add     rsp, 68h
0x18001db6c  pop     r15
0x18001db6e  pop     r14
0x18001db70  pop     rdi
0x18001db71  pop     rsi
0x18001db72  pop     rbp
0x18001db73  pop     rbx
0x18001db74  retn
```
