# InstallDeviceDriverUpdate

- ea: `0x14001a9f0`
- end: `0x14001ae45`
- name: `InstallDeviceDriverUpdate`
- size: `1109`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, struct _DRVUTILS_UPDATE_INFO *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x14001b8d8`

## callees

- `0x1400070bc`
- `0x140011a78`
- `0x140019cf4`
- `0x14001a9f0`
- `0x14001c160`
- `0x14001c22c`
- `0x140024d98`
- `0x1400270b4`
- `0x140027448`
- `0x14002c2bc`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001acbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001acd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001adfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001acbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001acd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001adfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ab2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ad2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ad92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ab2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ad2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ad92`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14001abd4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14001abd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001aa8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001aa8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001aa7d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ab50`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ab75`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ac3c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ac59`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001aca3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ad01`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ad47`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ad62`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001adaf`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ae1a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001aa7d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ab50`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ab75`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ac3c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ac59`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001aca3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ad01`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ad47`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ad62`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001adaf`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ae1a`

## string_xrefs

- `0x14001aa4f`: `{Update Device - %ws}`
- `0x14001ab9b`: `Driver does not need to be installed on device.`
- `0x14001ac8f`: `Failed to install driver on device. Error = 0x%08X`
- `0x14001ad31`: `Unable to mark non-present device for reinstall. Error = 0x%08X`
- `0x14001ad54`: `Non-present device needs reinstall.`
- `0x14001ad9d`: `Unable to mark hardware configuration for respecialize. Error = 0x%08X`
- `0x14001ae01`: `{Update Device - exit(0x%08X)}`

## pseudocode

```c
__int64 __fastcall InstallDeviceDriverUpdate(
        DEVINST a1,
        int *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        struct _DRVUTILS_UPDATE_INFO *a6,
        int *a7,
        unsigned __int64 a8)
{
  int v8; // r13d
  unsigned __int16 *v11; // r12
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rbx
  unsigned int v14; // edi
  int v15; // eax
  _WORD *v16; // rdi
  CONFIGRET DevNode_PropertyW; // r13d
  unsigned int v18; // eax
  void *v19; // r8
  DWORD LastError; // eax
  DWORD v21; // eax
  __int64 v22; // rax
  unsigned __int16 **v23; // rcx
  ULONG ulFlags[2]; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v27; // [rsp+48h] [rbp-B8h]
  ULONG PropertyBufferSize; // [rsp+60h] [rbp-A0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+64h] [rbp-9Ch] BYREF
  int v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+6Ch] [rbp-94h]
  wchar_t *Str; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  int *v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  int *v36; // [rsp+90h] [rbp-70h]
  __int64 v37[50]; // [rsp+A0h] [rbp-60h] BYREF

  v8 = 0;
  v36 = a7;
  v35 = a4;
  v33 = a3;
  v34 = a2;
  v11 = 0;
  Str = 0;
  v30 = 0;
  PropertyType = 1;
  PropertyBufferSize = 0;
  DevRtlWriteTextLog(a8, 1, 196612, "{Update Device - %ws}", a2);
  v12 = (unsigned __int16 *)LocalAlloc(0x40u, 0x3B8u);
  v13 = v12;
  if ( !v12 )
  {
    v14 = 14;
    goto LABEL_40;
  }
  v31 = 0;
  memset_0(v12, 0, 0x3B8u);
  StringCchCopyW(v13 + 8, 0xC8u, (size_t *)a2);
  if ( (unsigned int)DevUtilsIsDevicePresent(a1) )
  {
    *((_DWORD *)v13 + 104) |= 1u;
    LODWORD(v27) = 200;
    v15 = PnpUtilsSelectDriverForDevNode(
            0,
            a1,
            (int)a2,
            a6 != 0 ? 2 : 0,
            a6,
            (__int64)&Str,
            v26,
            0,
            (__int64)v37,
            v27,
            a8);
    v11 = Str;
    if ( !v15 )
    {
      ulFlags[0] = GetLastError();
      v14 = ulFlags[0];
      DevRtlWriteTextLog(
        a8,
        1,
        2,
        "Unable to determine best matching drivers for device '%ws'.  Err = 0x%08X",
        a2,
        *(_QWORD *)ulFlags);
LABEL_23:
      v19 = (void *)*((_QWORD *)v13 + 118);
      if ( v19 )
        HeapFree(hHeap, 0, v19);
      HeapFree(hHeap, 0, v13);
      goto LABEL_40;
    }
    if ( !*Str )
    {
      DevRtlWriteTextLog(a8, 1, 2, "No matching drivers found for device.");
LABEL_8:
      v14 = 0;
      goto LABEL_23;
    }
    if ( !(unsigned int)DrvUtilsDriverNodesContainInfName(Str, (wchar_t *)(v33 + 520)) )
    {
      DevRtlWriteTextLog(a8, 1, 2, "Driver does not need to be installed on device.");
      goto LABEL_8;
    }
    v16 = v13 + 210;
    PropertyBufferSize = 520;
    DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                          a1,
                          &DEVPKEY_Device_DriverInfPath,
                          &PropertyType,
                          (PBYTE)v13 + 420,
                          &PropertyBufferSize,
                          0);
    if ( DevNode_PropertyW || PropertyType != 18 )
      *v16 = 0;
    if ( *v16 )
      *((_QWORD *)v13 + 118) = GetDeviceDriverNodeStrongName(a1, 0);
    if ( DevNode_PropertyW == 37 )
    {
      DevRtlWriteTextLog(a8, 1, 4, "Current driver: <none>");
    }
    else if ( *((_QWORD *)v13 + 118) )
    {
      DevRtlWriteTextLog(a8, 1, 4, "Current driver: %ws", *((_QWORD *)v13 + 118));
    }
    else
    {
      DevRtlWriteTextLog(a8, 1, 2, "Unable to get the current driver in use by device.");
    }
    v18 = InstallSpecificDriver(v35, 0, v34, (__int64)v37, v11, a5 | 0x80000000);
    v14 = v18;
    if ( v18 )
    {
      DevRtlWriteTextLog(a8, 1, 1, "Failed to install driver on device. Error = 0x%08X", v18);
      goto LABEL_23;
    }
    if ( (unsigned int)DevUtilsDeviceNeedsReboot(a1) )
    {
      v8 = 1;
      DevRtlWriteTextLog(a8, 1, 4, "Device needs reboot.");
      *((_DWORD *)v13 + 104) |= 4u;
    }
    else
    {
      v8 = v31;
    }
  }
  else
  {
    v14 = 0;
    if ( (unsigned int)SetDeviceNeedsReinstall(a1, 1, &v30) )
    {
      DevRtlWriteTextLog(a8, 1, 4, "Non-present device needs reinstall.");
      if ( v30 )
        *((_DWORD *)v13 + 104) |= 2u;
    }
    else
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(a8, 1, 2, "Unable to mark non-present device for reinstall. Error = 0x%08X", LastError);
    }
  }
  if ( (v13[208] & 2) != 0 && !(unsigned int)SetDeviceHardwareConfigNeedsRespecialize(a1) )
  {
    v21 = GetLastError();
    DevRtlWriteTextLog(a8, 1, 2, "Unable to mark hardware configuration for respecialize. Error = 0x%08X", v21);
  }
  v22 = v33 + 1600;
  v23 = *(unsigned __int16 ***)(v33 + 1608);
  if ( *v23 != (unsigned __int16 *)(v33 + 1600) )
    __fastfail(3u);
  *(_QWORD *)v13 = v22;
  *((_QWORD *)v13 + 1) = v23;
  *v23 = v13;
  *(_QWORD *)(v22 + 8) = v13;
  if ( v36 )
    *v36 = v8;
LABEL_40:
  if ( v11 )
    HeapFree(hHeap, 0, v11);
  DevRtlWriteTextLog(a8, 1, 327684, "{Update Device - exit(0x%08X)}", v14);
  return v14;
}

```

## disassembly

```asm
0x14001a9f0  push    rbp
0x14001a9f2  push    rbx
0x14001a9f3  push    rsi
0x14001a9f4  push    rdi
0x14001a9f5  push    r12
0x14001a9f7  push    r13
0x14001a9f9  push    r14
0x14001a9fb  push    r15
0x14001a9fd  lea     rbp, [rsp-148h]
0x14001aa05  sub     rsp, 248h
0x14001aa0c  mov     rax, cs:__security_cookie
0x14001aa13  xor     rax, rsp
0x14001aa16  mov     [rbp+180h+var_50], rax
0x14001aa1d  mov     rax, [rbp+180h+arg_30]
0x14001aa24  xor     r13d, r13d
0x14001aa27  mov     rsi, [rbp+180h+arg_38]
0x14001aa2e  mov     r14, rdx
0x14001aa31  mov     rdi, [rbp+180h+arg_28]
0x14001aa38  mov     r15d, ecx
0x14001aa3b  mov     [rbp+180h+var_1F0], rax
0x14001aa3f  mov     rcx, rsi
0x14001aa42  lea     eax, [r13+1]
0x14001aa46  mov     [rbp+180h+var_1F8], r9
0x14001aa4a  mov     [rsp+280h+var_208], r8
0x14001aa4f  lea     r9, aUpdateDeviceWs; "{Update Device - %ws}"
0x14001aa56  mov     [rbp+180h+var_200], rdx
0x14001aa5a  mov     r8d, 30004h
0x14001aa60  mov     [rsp+280h+PropertyBufferSize], rdx
0x14001aa65  mov     r12d, r13d
0x14001aa68  mov     edx, eax
0x14001aa6a  mov     [rsp+280h+Str], r13
0x14001aa6f  mov     [rsp+280h+var_218], r13d
0x14001aa74  mov     [rsp+280h+PropertyType], eax
0x14001aa78  mov     [rsp+280h+var_220], r13d
0x14001aa7d  call    cs:__imp_DevRtlWriteTextLog
0x14001aa83  mov     edx, 3B8h; uBytes
0x14001aa88  lea     ecx, [r13+40h]; uFlags
0x14001aa8c  call    cs:__imp_LocalAlloc
0x14001aa92  mov     rbx, rax
0x14001aa95  test    rax, rax
0x14001aa98  jnz     short loc_14001AAA2
0x14001aa9a  lea     edi, [rax+0Eh]
0x14001aa9d  jmp     loc_14001ADEA
0x14001aaa2  xor     edx, edx; Val
0x14001aaa4  mov     [rsp+280h+var_214], r13d
0x14001aaa9  mov     r8d, 3B8h; Size
0x14001aaaf  mov     rcx, rbx; void *
0x14001aab2  call    memset_0
0x14001aab7  lea     rcx, [rbx+10h]; unsigned __int16 *
0x14001aabb  mov     r8, r14; unsigned __int16 *
0x14001aabe  mov     edx, 0C8h; unsigned __int64
0x14001aac3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001aac8  mov     ecx, r15d
0x14001aacb  call    DevUtilsIsDevicePresent
0x14001aad0  test    eax, eax
0x14001aad2  jz      loc_14001AD10
0x14001aad8  or      dword ptr [rbx+1A0h], 1
0x14001aadf  mov     rax, rdi
0x14001aae2  mov     [rsp+280h+var_230], rsi; unsigned __int64
0x14001aae7  neg     rax
0x14001aaea  mov     dword ptr [rsp+280h+var_238], 0C8h; unsigned __int64
0x14001aaf2  lea     rax, [rbp+180h+var_1E0]
0x14001aaf6  mov     [rsp+280h+var_240], rax; __int64
0x14001aafb  sbb     r9d, r9d
0x14001aafe  lea     rax, [rsp+280h+Str]
0x14001ab03  mov     [rsp+280h+var_248], r13; __int64
0x14001ab08  mov     qword ptr [rsp+280h+ulFlags], rax; __int64
0x14001ab0d  and     r9d, 2; int
0x14001ab11  mov     r8, r14; int
0x14001ab14  mov     [rsp+280h+PropertyBufferSize], rdi; struct _DRVUTILS_UPDATE_INFO *
0x14001ab19  mov     edx, r15d; int
0x14001ab1c  xor     ecx, ecx; int
0x14001ab1e  call    PnpUtilsSelectDriverForDevNode
0x14001ab23  mov     r12, [rsp+280h+Str]
0x14001ab28  test    eax, eax
0x14001ab2a  jnz     short loc_14001AB5B
0x14001ab2c  call    cs:__imp_GetLastError
0x14001ab32  mov     edx, 1
0x14001ab37  mov     [rsp+280h+ulFlags], eax
0x14001ab3b  lea     r9, aUnableToDeterm_8; "Unable to determine best matching drive"...
0x14001ab42  mov     [rsp+280h+PropertyBufferSize], r14
0x14001ab47  mov     rcx, rsi
0x14001ab4a  mov     edi, eax
0x14001ab4c  lea     r8d, [rdx+1]
0x14001ab50  call    cs:__imp_DevRtlWriteTextLog
0x14001ab56  jmp     loc_14001ACA9
0x14001ab5b  cmp     [r12], r13w
0x14001ab60  jnz     short loc_14001AB83
0x14001ab62  lea     r9, aNoMatchingDriv; "No matching drivers found for device."
0x14001ab69  mov     edx, 1
0x14001ab6e  mov     rcx, rsi
0x14001ab71  lea     r8d, [rdx+1]
0x14001ab75  call    cs:__imp_DevRtlWriteTextLog
0x14001ab7b  mov     edi, r13d
0x14001ab7e  jmp     loc_14001ACA9
0x14001ab83  mov     rdx, [rsp+280h+var_208]
0x14001ab88  mov     rcx, r12; Str
0x14001ab8b  add     rdx, 208h; String1
0x14001ab92  call    DrvUtilsDriverNodesContainInfName
0x14001ab97  test    eax, eax
0x14001ab99  jnz     short loc_14001ABA4
0x14001ab9b  lea     r9, aDriverDoesNotN; "Driver does not need to be installed on"...
0x14001aba2  jmp     short loc_14001AB69
0x14001aba4  lea     rax, [rsp+280h+var_220]
0x14001aba9  mov     [rsp+280h+ulFlags], r13d; ulFlags
0x14001abae  lea     rdi, [rbx+1A4h]
0x14001abb5  mov     [rsp+280h+var_220], 208h
0x14001abbd  mov     r9, rdi; PropertyBuffer
0x14001abc0  mov     [rsp+280h+PropertyBufferSize], rax; PropertyBufferSize
0x14001abc5  lea     r8, [rsp+280h+PropertyType]; PropertyType
0x14001abca  mov     ecx, r15d; dnDevInst
0x14001abcd  lea     rdx, DEVPKEY_Device_DriverInfPath; PropertyKey
0x14001abd4  call    cs:__imp_CM_Get_DevNode_PropertyW
0x14001abda  xor     edx, edx
0x14001abdc  mov     r13d, eax
0x14001abdf  test    eax, eax
0x14001abe1  jnz     short loc_14001ABEA
0x14001abe3  cmp     [rsp+280h+PropertyType], 12h
0x14001abe8  jz      short loc_14001ABED
0x14001abea  mov     [rdi], dx
0x14001abed  cmp     [rdi], dx
0x14001abf0  jz      short loc_14001AC01
0x14001abf2  mov     ecx, r15d
0x14001abf5  call    GetDeviceDriverNodeStrongName
0x14001abfa  mov     [rbx+3B0h], rax
0x14001ac01  mov     r14d, 4
0x14001ac07  cmp     r13d, 25h ; '%'
0x14001ac0b  jnz     short loc_14001AC19
0x14001ac0d  lea     r9, aCurrentDriverN; "Current driver: <none>"
0x14001ac14  mov     r8d, r14d
0x14001ac17  jmp     short loc_14001AC51
0x14001ac19  mov     rax, [rbx+3B0h]
0x14001ac20  test    rax, rax
0x14001ac23  jz      short loc_14001AC44
0x14001ac25  lea     r9, aCurrentDriverW; "Current driver: %ws"
0x14001ac2c  mov     [rsp+280h+PropertyBufferSize], rax
0x14001ac31  mov     r8d, r14d
0x14001ac34  mov     edx, 1
0x14001ac39  mov     rcx, rsi
0x14001ac3c  call    cs:__imp_DevRtlWriteTextLog
0x14001ac42  jmp     short loc_14001AC5F
0x14001ac44  lea     r9, aUnableToGetThe; "Unable to get the current driver in use"...
0x14001ac4b  mov     r8d, 2
0x14001ac51  mov     edx, 1
0x14001ac56  mov     rcx, rsi
0x14001ac59  call    cs:__imp_DevRtlWriteTextLog
0x14001ac5f  mov     eax, [rbp+180h+arg_20]
0x14001ac65  lea     r9, [rbp+180h+var_1E0]
0x14001ac69  mov     r8, [rbp+180h+var_200]
0x14001ac6d  bts     eax, 1Fh
0x14001ac71  mov     rcx, [rbp+180h+var_1F8]
0x14001ac75  xor     edx, edx
0x14001ac77  mov     [rsp+280h+ulFlags], eax
0x14001ac7b  mov     [rsp+280h+PropertyBufferSize], r12
0x14001ac80  call    InstallSpecificDriver
0x14001ac85  mov     edi, eax
0x14001ac87  test    eax, eax
0x14001ac89  jz      short loc_14001ACDB
0x14001ac8b  mov     dword ptr [rsp+280h+PropertyBufferSize], eax
0x14001ac8f  lea     r9, aFailedToInstal_3; "Failed to install driver on device. Err"...
0x14001ac96  mov     eax, 1
0x14001ac9b  mov     rcx, rsi
0x14001ac9e  mov     r8d, eax
0x14001aca1  mov     edx, eax
0x14001aca3  call    cs:__imp_DevRtlWriteTextLog
0x14001aca9  mov     r8, [rbx+3B0h]; lpMem
0x14001acb0  test    r8, r8
0x14001acb3  jz      short loc_14001ACC4
0x14001acb5  mov     rcx, cs:hHeap; hHeap
0x14001acbc  xor     edx, edx; dwFlags
0x14001acbe  call    cs:__imp_HeapFree
0x14001acc4  mov     rcx, cs:hHeap; hHeap
0x14001accb  mov     r8, rbx; lpMem
0x14001acce  xor     edx, edx; dwFlags
0x14001acd0  call    cs:__imp_HeapFree
0x14001acd6  jmp     loc_14001ADEA
0x14001acdb  mov     ecx, r15d
0x14001acde  call    DevUtilsDeviceNeedsReboot
0x14001ace3  test    eax, eax
0x14001ace5  jz      loc_14001AD78
0x14001aceb  mov     r13d, 1
0x14001acf1  lea     r9, aDeviceNeedsReb; "Device needs reboot."
0x14001acf8  mov     edx, r13d
0x14001acfb  mov     r8d, r14d
0x14001acfe  mov     rcx, rsi
0x14001ad01  call    cs:__imp_DevRtlWriteTextLog
0x14001ad07  or      [rbx+1A0h], r14d
0x14001ad0e  jmp     short loc_14001AD7D
0x14001ad10  xor     r14d, r14d
0x14001ad13  lea     r8, [rsp+280h+var_218]
0x14001ad18  mov     ecx, r15d
0x14001ad1b  mov     edi, r14d
0x14001ad1e  lea     edx, [r14+1]
0x14001ad22  call    SetDeviceNeedsReinstall
0x14001ad27  test    eax, eax
0x14001ad29  jnz     short loc_14001AD4F
0x14001ad2b  call    cs:__imp_GetLastError
0x14001ad31  lea     r9, aUnableToMarkNo; "Unable to mark non-present device for r"...
0x14001ad38  mov     rcx, rsi
0x14001ad3b  lea     edx, [r14+1]
0x14001ad3f  mov     dword ptr [rsp+280h+PropertyBufferSize], eax
0x14001ad43  lea     r8d, [r14+2]
0x14001ad47  call    cs:__imp_DevRtlWriteTextLog
0x14001ad4d  jmp     short loc_14001AD7D
0x14001ad4f  mov     edx, 1
0x14001ad54  lea     r9, aNonPresentDevi; "Non-present device needs reinstall."
0x14001ad5b  mov     rcx, rsi
0x14001ad5e  lea     r8d, [rdx+3]
0x14001ad62  call    cs:__imp_DevRtlWriteTextLog
0x14001ad68  cmp     [rsp+280h+var_218], r14d
0x14001ad6d  jz      short loc_14001AD7D
0x14001ad6f  or      dword ptr [rbx+1A0h], 2
0x14001ad76  jmp     short loc_14001AD7D
0x14001ad78  mov     r13d, [rsp+280h+var_214]
0x14001ad7d  test    byte ptr [rbx+1A0h], 2
0x14001ad84  jz      short loc_14001ADB5
0x14001ad86  mov     ecx, r15d
0x14001ad89  call    SetDeviceHardwareConfigNeedsRespecialize
0x14001ad8e  test    eax, eax
0x14001ad90  jnz     short loc_14001ADB5
0x14001ad92  call    cs:__imp_GetLastError
0x14001ad98  mov     edx, 1
0x14001ad9d  lea     r9, aUnableToMarkHa; "Unable to mark hardware configuration f"...
0x14001ada4  mov     rcx, rsi
0x14001ada7  mov     dword ptr [rsp+280h+PropertyBufferSize], eax
0x14001adab  lea     r8d, [rdx+1]
0x14001adaf  call    cs:__imp_DevRtlWriteTextLog
0x14001adb5  mov     rax, [rsp+280h+var_208]
0x14001adba  add     rax, 640h
0x14001adc0  mov     rcx, [rax+8]
0x14001adc4  cmp     [rcx], rax
0x14001adc7  jz      short loc_14001ADD0
0x14001adc9  mov     ecx, 3
0x14001adce  int     29h; Win8: RtlFailFast(ecx)
0x14001add0  mov     [rbx], rax
0x14001add3  mov     [rbx+8], rcx
0x14001add7  mov     [rcx], rbx
0x14001adda  mov     [rax+8], rbx
0x14001adde  mov     rax, [rbp+180h+var_1F0]
0x14001ade2  test    rax, rax
0x14001ade5  jz      short loc_14001ADEA
0x14001ade7  mov     [rax], r13d
0x14001adea  test    r12, r12
0x14001aded  jz      short loc_14001AE01
0x14001adef  mov     rcx, cs:hHeap; hHeap
0x14001adf6  mov     r8, r12; lpMem
0x14001adf9  xor     edx, edx; dwFlags
0x14001adfb  call    cs:__imp_HeapFree
0x14001ae01  lea     r9, aUpdateDeviceEx; "{Update Device - exit(0x%08X)}"
0x14001ae08  mov     dword ptr [rsp+280h+PropertyBufferSize], edi
0x14001ae0c  mov     edx, 1
0x14001ae11  mov     r8d, 50004h
0x14001ae17  mov     rcx, rsi
0x14001ae1a  call    cs:__imp_DevRtlWriteTextLog
0x14001ae20  mov     eax, edi
0x14001ae22  mov     rcx, [rbp+180h+var_50]
0x14001ae29  xor     rcx, rsp; StackCookie
0x14001ae2c  call    __security_check_cookie
0x14001ae31  add     rsp, 248h
0x14001ae38  pop     r15
0x14001ae3a  pop     r14
0x14001ae3c  pop     r13
0x14001ae3e  pop     r12
0x14001ae40  pop     rdi
0x14001ae41  pop     rsi
0x14001ae42  pop     rbx
0x14001ae43  pop     rbp
0x14001ae44  retn
```
