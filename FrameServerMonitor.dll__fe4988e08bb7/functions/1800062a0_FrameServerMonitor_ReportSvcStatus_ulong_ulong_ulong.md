# FrameServerMonitor::ReportSvcStatus(ulong,ulong,ulong)

- ea: `0x1800062a0`
- end: `0x180006365`
- name: `?ReportSvcStatus@FrameServerMonitor@@MEAAJKKK@Z`
- size: `197`
- prototype: `__int64 __fastcall(FrameServerMonitor *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800060f8`
- `0x1800062a0`
- `0x180006a98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006313`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006309`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006309`

## pseudocode

```c
__int64 __fastcall FrameServerMonitor::ReportSvcStatus(FrameServerMonitor *this, int a2, int a3, int a4)
{
  signed int v4; // ebx
  int v6; // eax
  int v7; // ecx
  SERVICE_STATUS_HANDLE v8; // rcx
  signed int LastError; // eax

  v4 = 0;
  if ( a2 != 1 )
  {
    if ( a2 == 2 || a2 == 3 )
    {
      *((_DWORD *)this + 24) = 0;
    }
    else if ( a2 == 4 )
    {
      *((_DWORD *)this + 24) = 1029;
      v6 = 0;
LABEL_8:
      v7 = v6 + 1;
      goto LABEL_10;
    }
    v6 = dword_18005D3B8;
    goto LABEL_8;
  }
  v6 = 0;
  *((_DWORD *)this + 24) = 1;
  v7 = 0;
LABEL_10:
  dword_18005D3B8 = v7;
  *((_DWORD *)this + 27) = v6;
  v8 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 10);
  *((_DWORD *)this + 23) = a2;
  *((_DWORD *)this + 25) = a3;
  *((_DWORD *)this + 28) = a4;
  if ( !SetServiceStatus(v8, (LPSERVICE_STATUS)((char *)this + 88)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids, this, v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800062a0  mov     [rsp+arg_0], rbx
0x1800062a5  push    rdi
0x1800062a6  sub     rsp, 30h
0x1800062aa  xor     ebx, ebx
0x1800062ac  mov     eax, edx
0x1800062ae  mov     r10d, edx
0x1800062b1  mov     rdi, rcx
0x1800062b4  sub     eax, 1
0x1800062b7  jz      short loc_1800062E1
0x1800062b9  sub     eax, 1
0x1800062bc  jz      short loc_1800062D3
0x1800062be  sub     eax, 1
0x1800062c1  jz      short loc_1800062D3
0x1800062c3  cmp     eax, 1
0x1800062c6  jnz     short loc_1800062D6
0x1800062c8  mov     dword ptr [rcx+60h], 405h
0x1800062cf  xor     eax, eax
0x1800062d1  jmp     short loc_1800062DC
0x1800062d3  mov     [rcx+60h], ebx
0x1800062d6  mov     eax, cs:dword_18005D3B8
0x1800062dc  lea     ecx, [rax+1]
0x1800062df  jmp     short loc_1800062EC
0x1800062e1  xor     eax, eax
0x1800062e3  mov     dword ptr [rcx+60h], 1
0x1800062ea  xor     ecx, ecx
0x1800062ec  mov     cs:dword_18005D3B8, ecx
0x1800062f2  lea     rdx, [rdi+58h]; lpServiceStatus
0x1800062f6  mov     [rdi+6Ch], eax
0x1800062f9  mov     rcx, [rdi+50h]; hServiceStatus
0x1800062fd  mov     [rdx+4], r10d
0x180006301  mov     [rdi+64h], r8d
0x180006305  mov     [rdi+70h], r9d
0x180006309  call    cs:__imp_SetServiceStatus
0x18000630f  test    eax, eax
0x180006311  jnz     short loc_180006358
0x180006313  call    cs:__imp_GetLastError
0x180006319  mov     ebx, eax
0x18000631b  test    eax, eax
0x18000631d  jle     short loc_180006328
0x18000631f  movzx   ebx, ax
0x180006322  or      ebx, 80070000h
0x180006328  test    ebx, ebx
0x18000632a  jns     short loc_180006358
0x18000632c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180006331  cmp     al, 1
0x180006333  jb      short loc_180006358
0x180006335  mov     rcx, cs:WPP_GLOBAL_Control
0x18000633c  lea     r8, WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids
0x180006343  mov     edx, 17h
0x180006348  mov     [rsp+38h+var_18], ebx
0x18000634c  mov     r9, rdi
0x18000634f  mov     rcx, [rcx+10h]
0x180006353  call    WPP_SF_qD
0x180006358  mov     eax, ebx
0x18000635a  mov     rbx, [rsp+38h+arg_0]
0x18000635f  add     rsp, 30h
0x180006363  pop     rdi
0x180006364  retn
```
