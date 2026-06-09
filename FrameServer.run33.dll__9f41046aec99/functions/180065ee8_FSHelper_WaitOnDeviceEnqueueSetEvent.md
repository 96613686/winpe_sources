# FSHelper_WaitOnDeviceEnqueueSetEvent

- ea: `0x180065ee8`
- end: `0x1800660cd`
- name: `FSHelper_WaitOnDeviceEnqueueSetEvent`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a7f0c`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x180065ee8`
- `0x1800660d4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065f68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065f68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180065ff6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180065ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066074`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066074`

## pseudocode

```c
__int64 __fastcall FSHelper_WaitOnDeviceEnqueueSetEvent(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  void *v3; // rdi
  signed int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v11; // eax
  __int64 v12; // rdx
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v14 = 0;
  if ( !a1 )
  {
    v5 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_25;
    v6 = 29;
    goto LABEL_24;
  }
  v7 = (**a1)(a1, &GUID_05008617_fbfd_4051_a790_144884b4f6a9, &v14);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_25;
    v8 = 30;
    goto LABEL_7;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v3 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4d7477ceb6fd3b3543efc10f2533cddc_Traceguids, 0, v5);
    if ( v5 >= 0 )
      goto LABEL_29;
    goto LABEL_25;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v14 + 128LL))(v14, EventW);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_25;
    v8 = 32;
LABEL_7:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_4d7477ceb6fd3b3543efc10f2533cddc_Traceguids, 0, v7);
    goto LABEL_25;
  }
  if ( !WaitForSingleObject(v3, 0xFFFFFFFF) )
    goto LABEL_28;
  v11 = GetLastError();
  v5 = v11;
  if ( v11 > 0 )
    v5 = (unsigned __int16)v11 | 0x80070000;
  if ( v5 >= 0 )
    goto LABEL_28;
  if ( !g_wppLevels )
    goto LABEL_25;
  v6 = 33;
LABEL_24:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_4d7477ceb6fd3b3543efc10f2533cddc_Traceguids, 0, v5);
LABEL_25:
  if ( byte_18010EC4D )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 34, &WPP_4d7477ceb6fd3b3543efc10f2533cddc_Traceguids, a1, v5);
  if ( v3 )
LABEL_28:
    CloseHandle(v3);
LABEL_29:
  if ( v5 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v12 = 36;
      goto LABEL_34;
    }
  }
  else if ( byte_18010EC4D )
  {
    v12 = 35;
LABEL_34:
    WPP_SF_DqD(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, a3, (unsigned int)v5, a1);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180065ee8  push    rbx
0x180065eea  push    rsi
0x180065eeb  push    rdi
0x180065eec  push    r14
0x180065eee  sub     rsp, 38h
0x180065ef2  xor     edi, edi
0x180065ef4  mov     [rsp+58h+arg_0], 0
0x180065efd  lea     r14, WPP_4d7477ceb6fd3b3543efc10f2533cddc_Traceguids
0x180065f04  mov     rsi, rcx
0x180065f07  test    rcx, rcx
0x180065f0a  jnz     short loc_180065F26
0x180065f0c  mov     ebx, 80004003h
0x180065f11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065f18  jb      loc_180066041
0x180065f1e  lea     edx, [rcx+1Dh]
0x180065f21  jmp     loc_180066027
0x180065f26  mov     rax, [rcx]
0x180065f29  lea     r8, [rsp+58h+arg_0]
0x180065f2e  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x180065f35  mov     rax, [rax]
0x180065f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f3d  mov     ebx, eax
0x180065f3f  test    eax, eax
0x180065f41  jns     short loc_180065F5E
0x180065f43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065f4a  jb      loc_180066041
0x180065f50  mov     edx, 1Eh
0x180065f55  mov     dword ptr [rsp+58h+var_38], eax
0x180065f59  jmp     loc_18006602B
0x180065f5e  xor     r9d, r9d; lpName
0x180065f61  xor     r8d, r8d; bInitialState
0x180065f64  xor     edx, edx; bManualReset
0x180065f66  xor     ecx, ecx; lpEventAttributes
0x180065f68  call    cs:__imp_CreateEventW
0x180065f6e  mov     rdi, rax
0x180065f71  test    rax, rax
0x180065f74  jnz     short loc_180065FC0
0x180065f76  call    cs:__imp_GetLastError
0x180065f7c  mov     ebx, eax
0x180065f7e  test    eax, eax
0x180065f80  jle     short loc_180065F8B
0x180065f82  movzx   ebx, ax
0x180065f85  or      ebx, 80070000h
0x180065f8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065f92  jb      short loc_180065FB3
0x180065f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f9b  mov     edx, 1Fh
0x180065fa0  xor     r9d, r9d
0x180065fa3  mov     dword ptr [rsp+58h+var_38], ebx
0x180065fa7  mov     r8, r14
0x180065faa  mov     rcx, [rcx+10h]
0x180065fae  call    WPP_SF_qD
0x180065fb3  test    ebx, ebx
0x180065fb5  js      loc_180066041
0x180065fbb  jmp     loc_18006607A
0x180065fc0  mov     rcx, [rsp+58h+arg_0]
0x180065fc5  mov     rdx, rdi
0x180065fc8  mov     rax, [rcx]
0x180065fcb  mov     rax, [rax+80h]
0x180065fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fd7  mov     ebx, eax
0x180065fd9  test    eax, eax
0x180065fdb  jns     short loc_180065FF0
0x180065fdd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065fe4  jb      short loc_180066041
0x180065fe6  mov     edx, 20h ; ' '
0x180065feb  jmp     loc_180065F55
0x180065ff0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180065ff3  mov     rcx, rdi; hHandle
0x180065ff6  call    cs:__imp_WaitForSingleObject
0x180065ffc  test    eax, eax
0x180065ffe  jz      short loc_180066071
0x180066000  call    cs:__imp_GetLastError
0x180066006  mov     ebx, eax
0x180066008  test    eax, eax
0x18006600a  jle     short loc_180066015
0x18006600c  movzx   ebx, ax
0x18006600f  or      ebx, 80070000h
0x180066015  test    ebx, ebx
0x180066017  jns     short loc_180066071
0x180066019  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066020  jb      short loc_180066041
0x180066022  mov     edx, 21h ; '!'
0x180066027  mov     dword ptr [rsp+58h+var_38], ebx
0x18006602b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066032  xor     r9d, r9d
0x180066035  mov     r8, r14
0x180066038  mov     rcx, [rcx+10h]
0x18006603c  call    WPP_SF_qD
0x180066041  cmp     cs:byte_18010EC4D, 1
0x180066048  jb      short loc_18006606C
0x18006604a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066051  mov     edx, 22h ; '"'
0x180066056  mov     r9, rsi
0x180066059  mov     dword ptr [rsp+58h+var_38], ebx
0x18006605d  mov     r8, r14
0x180066060  mov     rcx, [rcx+0D8h]
0x180066067  call    WPP_SF_qD
0x18006606c  test    rdi, rdi
0x18006606f  jz      short loc_18006607A
0x180066071  mov     rcx, rdi; hObject
0x180066074  call    cs:__imp_CloseHandle
0x18006607a  test    ebx, ebx
0x18006607c  jns     short loc_18006608E
0x18006607e  cmp     cs:byte_18010EC4D, 1
0x180066085  jb      short loc_1800660B7
0x180066087  mov     edx, 23h ; '#'
0x18006608c  jmp     short loc_18006609C
0x18006608e  cmp     cs:byte_18010EC4D, 8
0x180066095  jb      short loc_1800660B7
0x180066097  mov     edx, 24h ; '$'
0x18006609c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660a3  mov     r9d, ebx
0x1800660a6  mov     [rsp+58h+var_38], rsi
0x1800660ab  mov     rcx, [rcx+0D8h]
0x1800660b2  call    WPP_SF_DqD
0x1800660b7  lea     rcx, [rsp+58h+arg_0]; void *
0x1800660bc  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800660c1  mov     eax, ebx
0x1800660c3  add     rsp, 38h
0x1800660c7  pop     r14
0x1800660c9  pop     rdi
0x1800660ca  pop     rsi
0x1800660cb  pop     rbx
0x1800660cc  retn
```
