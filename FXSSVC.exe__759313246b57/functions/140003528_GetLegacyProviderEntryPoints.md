# GetLegacyProviderEntryPoints

- ea: `0x140003528`
- end: `0x1400038df`
- name: `GetLegacyProviderEntryPoints`
- size: `951`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003e50`

## callees

- `0x140003528`
- `0x140004c78`
- `0x140004ca8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400035b5`
- `KERNEL32!GetLastError` at `0x140003611`
- `KERNEL32!GetLastError` at `0x14000366d`
- `KERNEL32!GetLastError` at `0x1400036c9`
- `KERNEL32!GetLastError` at `0x140003725`
- `KERNEL32!GetLastError` at `0x140003779`
- `KERNEL32!GetLastError` at `0x1400037c6`
- `KERNEL32!GetLastError` at `0x1400035b5`
- `KERNEL32!GetLastError` at `0x140003611`
- `KERNEL32!GetLastError` at `0x14000366d`
- `KERNEL32!GetLastError` at `0x1400036c9`
- `KERNEL32!GetLastError` at `0x140003725`
- `KERNEL32!GetLastError` at `0x140003779`
- `KERNEL32!GetLastError` at `0x1400037c6`
- `KERNEL32!GetProcAddress` at `0x140003579`
- `KERNEL32!GetProcAddress` at `0x1400035d5`
- `KERNEL32!GetProcAddress` at `0x140003631`
- `KERNEL32!GetProcAddress` at `0x14000368d`
- `KERNEL32!GetProcAddress` at `0x1400036e9`
- `KERNEL32!GetProcAddress` at `0x140003745`
- `KERNEL32!GetProcAddress` at `0x140003796`
- `KERNEL32!GetProcAddress` at `0x1400037fe`
- `KERNEL32!GetProcAddress` at `0x140003847`
- `KERNEL32!GetProcAddress` at `0x140003890`
- `KERNEL32!GetProcAddress` at `0x140003579`
- `KERNEL32!GetProcAddress` at `0x1400035d5`
- `KERNEL32!GetProcAddress` at `0x140003631`
- `KERNEL32!GetProcAddress` at `0x14000368d`
- `KERNEL32!GetProcAddress` at `0x1400036e9`
- `KERNEL32!GetProcAddress` at `0x140003745`
- `KERNEL32!GetProcAddress` at `0x140003796`
- `KERNEL32!GetProcAddress` at `0x1400037fe`
- `KERNEL32!GetProcAddress` at `0x140003847`
- `KERNEL32!GetProcAddress` at `0x140003890`

## string_xrefs

- `0x14000383d`: `FaxExtInitializeConfig`

## pseudocode

```c
__int64 __fastcall GetLegacyProviderEntryPoints(HMODULE hModule, _QWORD *a2)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  ProcAddress = GetProcAddress(hModule, "FaxDevInitialize");
  a2[270] = ProcAddress;
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 39;
LABEL_40:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_200271385d87382553faba38592a1280_Traceguids, LastError);
    return 0;
  }
  v7 = GetProcAddress(hModule, "FaxDevStartJob");
  a2[271] = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 40;
    goto LABEL_40;
  }
  v8 = GetProcAddress(hModule, "FaxDevEndJob");
  a2[272] = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 41;
    goto LABEL_40;
  }
  v9 = GetProcAddress(hModule, "FaxDevSend");
  a2[273] = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 42;
    goto LABEL_40;
  }
  v10 = GetProcAddress(hModule, "FaxDevReceive");
  a2[274] = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 43;
    goto LABEL_40;
  }
  v11 = GetProcAddress(hModule, "FaxDevReportStatus");
  a2[275] = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 44;
    goto LABEL_40;
  }
  v12 = GetProcAddress(hModule, "FaxDevAbortOperation");
  a2[276] = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 45;
    goto LABEL_40;
  }
  v14 = GetProcAddress(hModule, "FaxDevVirtualDeviceCreation");
  a2[278] = v14;
  if ( !v14
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  v15 = GetProcAddress(hModule, "FaxExtInitializeConfig");
  a2[280] = v15;
  if ( !v15
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  v16 = GetProcAddress(hModule, "FaxDevShutdown");
  a2[279] = v16;
  if ( !v16
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x140003528  push    rbx
0x14000352a  push    rbp
0x14000352b  push    rdi
0x14000352c  push    r14
0x14000352e  sub     rsp, 28h
0x140003532  mov     rbx, rdx
0x140003535  mov     rdi, rcx
0x140003538  mov     rcx, cs:WPP_GLOBAL_Control
0x14000353f  lea     rbp, WPP_GLOBAL_Control
0x140003546  lea     r14, WPP_200271385d87382553faba38592a1280_Traceguids
0x14000354d  cmp     rcx, rbp
0x140003550  jz      short loc_14000356F
0x140003552  test    byte ptr [rcx+1Ch], 4
0x140003556  jz      short loc_14000356F
0x140003558  cmp     byte ptr [rcx+19h], 5
0x14000355c  jb      short loc_14000356F
0x14000355e  mov     rcx, [rcx+10h]
0x140003562  mov     edx, 26h ; '&'
0x140003567  mov     r8, r14
0x14000356a  call    WPP_SF_
0x14000356f  lea     rdx, ProcName; "FaxDevInitialize"
0x140003576  mov     rcx, rdi; hModule
0x140003579  call    cs:__imp_GetProcAddress
0x140003580  nop     dword ptr [rax+rax+00h]
0x140003585  mov     [rbx+870h], rax
0x14000358c  test    rax, rax
0x14000358f  jnz     short loc_1400035CB
0x140003591  mov     rax, cs:WPP_GLOBAL_Control
0x140003598  cmp     rax, rbp
0x14000359b  jz      loc_1400037ED
0x1400035a1  test    byte ptr [rax+1Ch], 4
0x1400035a5  jz      loc_1400037ED
0x1400035ab  cmp     byte ptr [rax+19h], 2
0x1400035af  jb      loc_1400037ED
0x1400035b5  call    cs:__imp_GetLastError
0x1400035bc  nop     dword ptr [rax+rax+00h]
0x1400035c1  mov     edx, 27h ; '''
0x1400035c6  jmp     loc_1400037D7
0x1400035cb  lea     rdx, aFaxdevstartjob; "FaxDevStartJob"
0x1400035d2  mov     rcx, rdi; hModule
0x1400035d5  call    cs:__imp_GetProcAddress
0x1400035dc  nop     dword ptr [rax+rax+00h]
0x1400035e1  mov     [rbx+878h], rax
0x1400035e8  test    rax, rax
0x1400035eb  jnz     short loc_140003627
0x1400035ed  mov     rax, cs:WPP_GLOBAL_Control
0x1400035f4  cmp     rax, rbp
0x1400035f7  jz      loc_1400037ED
0x1400035fd  test    byte ptr [rax+1Ch], 4
0x140003601  jz      loc_1400037ED
0x140003607  cmp     byte ptr [rax+19h], 2
0x14000360b  jb      loc_1400037ED
0x140003611  call    cs:__imp_GetLastError
0x140003618  nop     dword ptr [rax+rax+00h]
0x14000361d  mov     edx, 28h ; '('
0x140003622  jmp     loc_1400037D7
0x140003627  lea     rdx, aFaxdevendjob; "FaxDevEndJob"
0x14000362e  mov     rcx, rdi; hModule
0x140003631  call    cs:__imp_GetProcAddress
0x140003638  nop     dword ptr [rax+rax+00h]
0x14000363d  mov     [rbx+880h], rax
0x140003644  test    rax, rax
0x140003647  jnz     short loc_140003683
0x140003649  mov     rax, cs:WPP_GLOBAL_Control
0x140003650  cmp     rax, rbp
0x140003653  jz      loc_1400037ED
0x140003659  test    byte ptr [rax+1Ch], 4
0x14000365d  jz      loc_1400037ED
0x140003663  cmp     byte ptr [rax+19h], 2
0x140003667  jb      loc_1400037ED
0x14000366d  call    cs:__imp_GetLastError
0x140003674  nop     dword ptr [rax+rax+00h]
0x140003679  mov     edx, 29h ; ')'
0x14000367e  jmp     loc_1400037D7
0x140003683  lea     rdx, aFaxdevsend; "FaxDevSend"
0x14000368a  mov     rcx, rdi; hModule
0x14000368d  call    cs:__imp_GetProcAddress
0x140003694  nop     dword ptr [rax+rax+00h]
0x140003699  mov     [rbx+888h], rax
0x1400036a0  test    rax, rax
0x1400036a3  jnz     short loc_1400036DF
0x1400036a5  mov     rax, cs:WPP_GLOBAL_Control
0x1400036ac  cmp     rax, rbp
0x1400036af  jz      loc_1400037ED
0x1400036b5  test    byte ptr [rax+1Ch], 4
0x1400036b9  jz      loc_1400037ED
0x1400036bf  cmp     byte ptr [rax+19h], 2
0x1400036c3  jb      loc_1400037ED
0x1400036c9  call    cs:__imp_GetLastError
0x1400036d0  nop     dword ptr [rax+rax+00h]
0x1400036d5  mov     edx, 2Ah ; '*'
0x1400036da  jmp     loc_1400037D7
0x1400036df  lea     rdx, aFaxdevreceive; "FaxDevReceive"
0x1400036e6  mov     rcx, rdi; hModule
0x1400036e9  call    cs:__imp_GetProcAddress
0x1400036f0  nop     dword ptr [rax+rax+00h]
0x1400036f5  mov     [rbx+890h], rax
0x1400036fc  test    rax, rax
0x1400036ff  jnz     short loc_14000373B
0x140003701  mov     rax, cs:WPP_GLOBAL_Control
0x140003708  cmp     rax, rbp
0x14000370b  jz      loc_1400037ED
0x140003711  test    byte ptr [rax+1Ch], 4
0x140003715  jz      loc_1400037ED
0x14000371b  cmp     byte ptr [rax+19h], 2
0x14000371f  jb      loc_1400037ED
0x140003725  call    cs:__imp_GetLastError
0x14000372c  nop     dword ptr [rax+rax+00h]
0x140003731  mov     edx, 2Bh ; '+'
0x140003736  jmp     loc_1400037D7
0x14000373b  lea     rdx, aFaxdevreportst; "FaxDevReportStatus"
0x140003742  mov     rcx, rdi; hModule
0x140003745  call    cs:__imp_GetProcAddress
0x14000374c  nop     dword ptr [rax+rax+00h]
0x140003751  mov     [rbx+898h], rax
0x140003758  test    rax, rax
0x14000375b  jnz     short loc_14000378C
0x14000375d  mov     rax, cs:WPP_GLOBAL_Control
0x140003764  cmp     rax, rbp
0x140003767  jz      loc_1400037ED
0x14000376d  test    byte ptr [rax+1Ch], 4
0x140003771  jz      short loc_1400037ED
0x140003773  cmp     byte ptr [rax+19h], 2
0x140003777  jb      short loc_1400037ED
0x140003779  call    cs:__imp_GetLastError
0x140003780  nop     dword ptr [rax+rax+00h]
0x140003785  mov     edx, 2Ch ; ','
0x14000378a  jmp     short loc_1400037D7
0x14000378c  lea     rdx, aFaxdevabortope; "FaxDevAbortOperation"
0x140003793  mov     rcx, rdi; hModule
0x140003796  call    cs:__imp_GetProcAddress
0x14000379d  nop     dword ptr [rax+rax+00h]
0x1400037a2  mov     [rbx+8A0h], rax
0x1400037a9  test    rax, rax
0x1400037ac  jnz     short loc_1400037F4
0x1400037ae  mov     rax, cs:WPP_GLOBAL_Control
0x1400037b5  cmp     rax, rbp
0x1400037b8  jz      short loc_1400037ED
0x1400037ba  test    byte ptr [rax+1Ch], 4
0x1400037be  jz      short loc_1400037ED
0x1400037c0  cmp     byte ptr [rax+19h], 2
0x1400037c4  jb      short loc_1400037ED
0x1400037c6  call    cs:__imp_GetLastError
0x1400037cd  nop     dword ptr [rax+rax+00h]
0x1400037d2  mov     edx, 2Dh ; '-'
0x1400037d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037de  mov     r9d, eax
0x1400037e1  mov     r8, r14
0x1400037e4  mov     rcx, [rcx+10h]
0x1400037e8  call    WPP_SF_d
0x1400037ed  xor     eax, eax
0x1400037ef  jmp     loc_1400038D4
0x1400037f4  lea     rdx, aFaxdevvirtuald; "FaxDevVirtualDeviceCreation"
0x1400037fb  mov     rcx, rdi; hModule
0x1400037fe  call    cs:__imp_GetProcAddress
0x140003805  nop     dword ptr [rax+rax+00h]
0x14000380a  mov     [rbx+8B0h], rax
0x140003811  test    rax, rax
0x140003814  jnz     short loc_14000383D
0x140003816  mov     rcx, cs:WPP_GLOBAL_Control
0x14000381d  cmp     rcx, rbp
0x140003820  jz      short loc_14000383D
0x140003822  test    byte ptr [rcx+1Ch], 4
0x140003826  jz      short loc_14000383D
0x140003828  cmp     byte ptr [rcx+19h], 5
0x14000382c  jb      short loc_14000383D
0x14000382e  mov     rcx, [rcx+10h]
0x140003832  lea     edx, [rax+2Eh]
0x140003835  mov     r8, r14
0x140003838  call    WPP_SF_
0x14000383d  lea     rdx, aFaxextinitiali; "FaxExtInitializeConfig"
0x140003844  mov     rcx, rdi; hModule
0x140003847  call    cs:__imp_GetProcAddress
0x14000384e  nop     dword ptr [rax+rax+00h]
0x140003853  mov     [rbx+8C0h], rax
0x14000385a  test    rax, rax
0x14000385d  jnz     short loc_140003886
0x14000385f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003866  cmp     rcx, rbp
0x140003869  jz      short loc_140003886
0x14000386b  test    byte ptr [rcx+1Ch], 4
0x14000386f  jz      short loc_140003886
0x140003871  cmp     byte ptr [rcx+19h], 5
0x140003875  jb      short loc_140003886
0x140003877  mov     rcx, [rcx+10h]
0x14000387b  lea     edx, [rax+2Fh]
0x14000387e  mov     r8, r14
0x140003881  call    WPP_SF_
0x140003886  lea     rdx, aFaxdevshutdown; "FaxDevShutdown"
0x14000388d  mov     rcx, rdi; hModule
0x140003890  call    cs:__imp_GetProcAddress
0x140003897  nop     dword ptr [rax+rax+00h]
0x14000389c  mov     [rbx+8B8h], rax
0x1400038a3  test    rax, rax
0x1400038a6  jnz     short loc_1400038CF
0x1400038a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038af  cmp     rcx, rbp
0x1400038b2  jz      short loc_1400038CF
0x1400038b4  test    byte ptr [rcx+1Ch], 4
0x1400038b8  jz      short loc_1400038CF
0x1400038ba  cmp     byte ptr [rcx+19h], 5
0x1400038be  jb      short loc_1400038CF
0x1400038c0  mov     rcx, [rcx+10h]
0x1400038c4  lea     edx, [rax+30h]
0x1400038c7  mov     r8, r14
0x1400038ca  call    WPP_SF_
0x1400038cf  mov     eax, 1
0x1400038d4  add     rsp, 28h
0x1400038d8  pop     r14
0x1400038da  pop     rdi
0x1400038db  pop     rbp
0x1400038dc  pop     rbx
0x1400038dd  retn
```
