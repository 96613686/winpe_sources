# PnpUtilsGetMatchingDevices

- ea: `0x14002bff4`
- end: `0x14002c2b3`
- name: `PnpUtilsGetMatchingDevices`
- size: `703`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1400161bc`
- `0x14001dc80`

## callees

- `0x1400070bc`
- `0x14000bcbc`
- `0x14000c354`
- `0x1400271b8`
- `0x14002b7ec`
- `0x14002bff4`
- `0x140045f30`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002c224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002c224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c143`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14002c16e`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14002c16e`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c087`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c198`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c212`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c250`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c28a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c087`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c198`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c212`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c250`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c28a`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002c112`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002c112`
- `drvstore!DriverStoreOpenW` at `0x14002c059`
- `drvstore!DriverStoreOpenW` at `0x14002c059`
- `drvstore!DriverStoreClose` at `0x14002c265`
- `drvstore!DriverStoreClose` at `0x14002c265`

## string_xrefs

- `0x14002c07e`: `Failed to open driver store. Error = 0x%08x`

## pseudocode

```c
__int64 __fastcall PnpUtilsGetMatchingDevices(
        __int64 a1,
        size_t *a2,
        __int64 (__fastcall *a3)(WCHAR *, __int64),
        __int64 a4,
        __int64 a5)
{
  DWORD LastError; // ebx
  __int64 v8; // rsi
  __int64 FileTitle; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 DeviceIdList; // rax
  void *v15; // r14
  WCHAR *i; // rdi
  CONFIGRET v17; // eax
  DWORD v18; // eax
  __int64 v19; // rax
  _BYTE *v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h]
  unsigned int *v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h]
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  DEVNODE pdnDevInst; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 (__fastcall *v29)(WCHAR *, __int64); // [rsp+68h] [rbp-98h]
  unsigned __int16 v30[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v31[528]; // [rsp+280h] [rbp+180h] BYREF

  v28 = a4;
  v29 = a3;
  v26 = 0;
  v25 = 0;
  pdnDevInst = 0;
  if ( !a3 )
  {
    LastError = 87;
LABEL_31:
    DevRtlWriteTextLog(a5, 1, 2, "Unable to find devices that match INF - (%08x)!", LastError);
    return LastError;
  }
  if ( a1 )
  {
    v8 = a1;
  }
  else
  {
    v8 = DriverStoreOpenW(0, 0, 0, 0);
    if ( !v8 )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(a5, 1, 1, "Failed to open driver store. Error = 0x%08x", LastError);
      goto LABEL_30;
    }
  }
  if ( (int)StringCchCopyW(v30, 0x104u, a2) >= 0
    && (unsigned int)pSetupTrimFileTitle(v30)
    && (FileTitle = pSetupGetFileTitle(v30)) != 0 )
  {
    LODWORD(v24) = 0;
    v23 = &v25;
    LODWORD(v22) = 520;
    v21 = v31;
    if ( (unsigned int)DriverStoreGetObjectPropertyW(v8, 2, FileTitle, DEVPKEY_DriverPackage_DriverInfName)
      && v25 >= 2
      && v26 == 18 )
    {
      DeviceIdList = DevUtilsGetDeviceIdList(v11, v10, v12, v13, &v26);
      v15 = (void *)DeviceIdList;
      if ( DeviceIdList )
      {
        LastError = 0;
        for ( i = (WCHAR *)DeviceIdList; *i; i += v19 + 1 )
        {
          v17 = CM_Locate_DevNodeW(&pdnDevInst, i, 1u);
          if ( v17 )
          {
            LODWORD(v21) = v17;
            DevRtlWriteTextLog(a5, 1, 2, "Unable to locate device '%ws'. cr = 0x%02X", i, v21, v22, v23, v24);
          }
          else if ( (unsigned int)PnpUtilsDriverPackageAppliesToDevNode(v8, pdnDevInst, a2, v31) )
          {
            v18 = v29(i, v28);
            LastError = v18;
            if ( v18 )
            {
              LODWORD(v21) = v18;
              DevRtlWriteTextLog(
                a5,
                1,
                5,
                "Matching devices callback for device '%ws' returned error (0x%08X).",
                i,
                v21,
                v22,
                v23,
                v24);
              break;
            }
          }
          v19 = -1;
          do
            ++v19;
          while ( i[v19] );
        }
        HeapFree(hHeap, 0, v15);
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 1168;
      LODWORD(v21) = 1168;
      DevRtlWriteTextLog(
        a5,
        1,
        1,
        "Failed to get published INF for driver package '%ws'. Error = 0x%08x",
        a2,
        v21,
        520,
        &v25,
        0);
    }
  }
  else
  {
    LastError = 87;
  }
  if ( !a1 )
    DriverStoreClose(v8);
LABEL_30:
  if ( LastError )
    goto LABEL_31;
  return LastError;
}

```

## disassembly

```asm
0x14002bff4  push    rbp
0x14002bff6  push    rbx
0x14002bff7  push    rsi
0x14002bff8  push    rdi
0x14002bff9  push    r12
0x14002bffb  push    r13
0x14002bffd  push    r14
0x14002bfff  lea     rbp, [rsp-3A0h]
0x14002c007  sub     rsp, 4A0h
0x14002c00e  mov     rax, cs:__security_cookie
0x14002c015  xor     rax, rsp
0x14002c018  mov     [rbp+3D0h+var_40], rax
0x14002c01f  xor     edi, edi
0x14002c021  mov     [rsp+4D0h+var_470], r9
0x14002c026  mov     [rsp+4D0h+var_468], r8
0x14002c02b  mov     r13, rdx
0x14002c02e  mov     [rsp+4D0h+var_47C], edi
0x14002c032  mov     r12, rcx
0x14002c035  mov     [rsp+4D0h+var_480], edi
0x14002c039  mov     [rsp+4D0h+pdnDevInst], edi
0x14002c03d  test    r8, r8
0x14002c040  jnz     short loc_14002C04A
0x14002c042  lea     ebx, [rdi+57h]
0x14002c045  jmp     loc_14002C26F
0x14002c04a  test    r12, r12
0x14002c04d  jnz     short loc_14002C092
0x14002c04f  xor     r9d, r9d
0x14002c052  xor     r8d, r8d
0x14002c055  xor     edx, edx
0x14002c057  xor     ecx, ecx
0x14002c059  call    cs:__imp_DriverStoreOpenW
0x14002c05f  mov     rsi, rax
0x14002c062  test    rax, rax
0x14002c065  jnz     short loc_14002C095
0x14002c067  call    cs:__imp_GetLastError
0x14002c06d  mov     rcx, [rbp+3D0h+arg_20]
0x14002c074  lea     edx, [rsi+1]
0x14002c077  mov     r8d, edx
0x14002c07a  mov     dword ptr [rsp+4D0h+var_4B0], eax
0x14002c07e  lea     r9, aFailedToOpenDr_2; "Failed to open driver store. Error = 0x"...
0x14002c085  mov     ebx, eax
0x14002c087  call    cs:__imp_DevRtlWriteTextLog
0x14002c08d  jmp     loc_14002C26B
0x14002c092  mov     rsi, r12
0x14002c095  mov     r8, r13; unsigned __int16 *
0x14002c098  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x14002c09d  mov     edx, 104h; unsigned __int64
0x14002c0a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002c0a7  test    eax, eax
0x14002c0a9  js      loc_14002C258
0x14002c0af  lea     rcx, [rsp+4D0h+var_460]
0x14002c0b4  call    pSetupTrimFileTitle
0x14002c0b9  test    eax, eax
0x14002c0bb  jz      loc_14002C258
0x14002c0c1  lea     rcx, [rsp+4D0h+var_460]
0x14002c0c6  call    pSetupGetFileTitle
0x14002c0cb  test    rax, rax
0x14002c0ce  jz      loc_14002C258
0x14002c0d4  mov     [rsp+4D0h+var_490], edi
0x14002c0d8  lea     rcx, [rsp+4D0h+var_480]
0x14002c0dd  mov     [rsp+4D0h+var_498], rcx
0x14002c0e2  lea     r9, DEVPKEY_DriverPackage_DriverInfName
0x14002c0e9  lea     rcx, [rbp+3D0h+var_250]
0x14002c0f0  mov     dword ptr [rsp+4D0h+var_4A0], 208h
0x14002c0f8  mov     [rsp+4D0h+var_4A8], rcx
0x14002c0fd  mov     r8, rax
0x14002c100  lea     rcx, [rsp+4D0h+var_47C]
0x14002c105  mov     edx, 2
0x14002c10a  mov     [rsp+4D0h+var_4B0], rcx
0x14002c10f  mov     rcx, rsi
0x14002c112  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002c118  test    eax, eax
0x14002c11a  jz      loc_14002C22C
0x14002c120  cmp     [rsp+4D0h+var_480], 2
0x14002c125  jb      loc_14002C22C
0x14002c12b  cmp     [rsp+4D0h+var_47C], 12h
0x14002c130  jnz     loc_14002C22C
0x14002c136  call    DevUtilsGetDeviceIdList
0x14002c13b  mov     r14, rax
0x14002c13e  test    rax, rax
0x14002c141  jnz     short loc_14002C150
0x14002c143  call    cs:__imp_GetLastError
0x14002c149  mov     ebx, eax
0x14002c14b  jmp     loc_14002C25D
0x14002c150  mov     ebx, edi
0x14002c152  xor     ecx, ecx
0x14002c154  mov     rdi, r14
0x14002c157  cmp     [rdi], cx
0x14002c15a  jz      loc_14002C218
0x14002c160  mov     r8d, 1; ulFlags
0x14002c166  lea     rcx, [rsp+4D0h+pdnDevInst]; pdnDevInst
0x14002c16b  mov     rdx, rdi; pDeviceID
0x14002c16e  call    cs:__imp_CM_Locate_DevNodeW
0x14002c174  test    eax, eax
0x14002c176  jz      short loc_14002C1A2
0x14002c178  mov     rcx, [rbp+3D0h+arg_20]
0x14002c17f  lea     r9, aUnableToLocate_1; "Unable to locate device '%ws'. cr = 0x%"...
0x14002c186  mov     edx, 1
0x14002c18b  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x14002c18f  mov     [rsp+4D0h+var_4B0], rdi
0x14002c194  lea     r8d, [rdx+1]
0x14002c198  call    cs:__imp_DevRtlWriteTextLog
0x14002c19e  xor     ecx, ecx
0x14002c1a0  jmp     short loc_14002C1D8
0x14002c1a2  mov     edx, [rsp+4D0h+pdnDevInst]
0x14002c1a6  lea     r9, [rbp+3D0h+var_250]
0x14002c1ad  mov     r8, r13
0x14002c1b0  mov     rcx, rsi
0x14002c1b3  call    PnpUtilsDriverPackageAppliesToDevNode
0x14002c1b8  xor     ecx, ecx
0x14002c1ba  test    eax, eax
0x14002c1bc  jz      short loc_14002C1D8
0x14002c1be  mov     rdx, [rsp+4D0h+var_470]
0x14002c1c3  mov     rcx, rdi
0x14002c1c6  mov     rax, [rsp+4D0h+var_468]
0x14002c1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c1d0  xor     ecx, ecx
0x14002c1d2  mov     ebx, eax
0x14002c1d4  test    eax, eax
0x14002c1d6  jnz     short loc_14002C1F2
0x14002c1d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002c1dc  inc     rax
0x14002c1df  cmp     [rdi+rax*2], cx
0x14002c1e3  jnz     short loc_14002C1DC
0x14002c1e5  lea     rdi, [rdi+rax*2]
0x14002c1e9  add     rdi, 2
0x14002c1ed  jmp     loc_14002C157
0x14002c1f2  mov     rcx, [rbp+3D0h+arg_20]
0x14002c1f9  lea     r9, aMatchingDevice; "Matching devices callback for device '%"...
0x14002c200  mov     edx, 1
0x14002c205  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x14002c209  mov     [rsp+4D0h+var_4B0], rdi
0x14002c20e  lea     r8d, [rdx+4]
0x14002c212  call    cs:__imp_DevRtlWriteTextLog
0x14002c218  mov     rcx, cs:hHeap; hHeap
0x14002c21f  mov     r8, r14; lpMem
0x14002c222  xor     edx, edx; dwFlags
0x14002c224  call    cs:__imp_HeapFree
0x14002c22a  jmp     short loc_14002C25D
0x14002c22c  mov     rcx, [rbp+3D0h+arg_20]
0x14002c233  lea     r9, aFailedToGetPub; "Failed to get published INF for driver "...
0x14002c23a  mov     edx, 1
0x14002c23f  mov     ebx, 490h
0x14002c244  mov     dword ptr [rsp+4D0h+var_4A8], ebx
0x14002c248  mov     r8d, edx
0x14002c24b  mov     [rsp+4D0h+var_4B0], r13
0x14002c250  call    cs:__imp_DevRtlWriteTextLog
0x14002c256  jmp     short loc_14002C25D
0x14002c258  mov     ebx, 57h ; 'W'
0x14002c25d  test    r12, r12
0x14002c260  jnz     short loc_14002C26B
0x14002c262  mov     rcx, rsi
0x14002c265  call    cs:__imp_DriverStoreClose
0x14002c26b  test    ebx, ebx
0x14002c26d  jz      short loc_14002C290
0x14002c26f  mov     rcx, [rbp+3D0h+arg_20]
0x14002c276  lea     r9, aUnableToFindDe; "Unable to find devices that match INF -"...
0x14002c27d  mov     edx, 1
0x14002c282  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x14002c286  lea     r8d, [rdx+1]
0x14002c28a  call    cs:__imp_DevRtlWriteTextLog
0x14002c290  mov     eax, ebx
0x14002c292  mov     rcx, [rbp+3D0h+var_40]
0x14002c299  xor     rcx, rsp; StackCookie
0x14002c29c  call    __security_check_cookie
0x14002c2a1  add     rsp, 4A0h
0x14002c2a8  pop     r14
0x14002c2aa  pop     r13
0x14002c2ac  pop     r12
0x14002c2ae  pop     rdi
0x14002c2af  pop     rsi
0x14002c2b0  pop     rbx
0x14002c2b1  pop     rbp
0x14002c2b2  retn
```
