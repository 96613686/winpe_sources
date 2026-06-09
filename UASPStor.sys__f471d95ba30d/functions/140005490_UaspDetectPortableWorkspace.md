# UaspDetectPortableWorkspace

- ea: `0x140005490`
- end: `0x14000573b`
- name: `UaspDetectPortableWorkspace`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004120`

## callees

- `0x140002a24`
- `0x140005490`
- `0x14000d7f0`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140005579`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000567c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140005579`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000567c`
- `ntoskrnl!PoDisableSleepStates` at `0x1400056b5`
- `ntoskrnl!PoDisableSleepStates` at `0x1400056b5`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400055ac`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400055ac`
- `ntoskrnl!_wcsnicmp` at `0x1400055d1`
- `ntoskrnl!_wcsnicmp` at `0x1400055d1`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x140005500`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x140005500`
- `ntoskrnl!RtlSetPortableOperatingSystem` at `0x1400055e6`
- `ntoskrnl!RtlSetPortableOperatingSystem` at `0x1400055e6`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400056f0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400056f0`

## string_xrefs

- `0x140005553`: `\Registry\Machine\System\CurrentControlSet\Enum\HTREE\ROOT\0`
- `0x140005659`: `\Registry\Machine\System\CurrentControlSet\Policies\Microsoft\PortableOperatingSystem`

## pseudocode

```c
int __fastcall UaspDetectPortableWorkspace(__int64 a1)
{
  _UNKNOWN **v2; // rax
  int v3; // ebx
  int RegistryValues; // eax
  int v5; // ecx
  int Default; // eax
  int v7; // edx
  bool v9[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[22]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Str2[80]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t PropertyBuffer[80]; // [rsp+1B0h] [rbp+B0h] BYREF

  v11 = 0;
  v10 = 0;
  v9[0] = 0;
  memset(Str2, 0, 0x9Au);
  ResultLength = 0;
  v14 = 0;
  v13 = 0;
  LODWORD(v2) = RtlCheckPortableOperatingSystem(v9);
  v3 = (int)v2;
  if ( (_DWORD)v2 == -1073741275 )
  {
    memset(v15, 0, 0xA8u);
    LODWORD(v13) = 10092544;
    *((_QWORD *)&v13 + 1) = Str2;
    LODWORD(v15[1]) = 292;
    v15[2] = L"ContainerID";
    LODWORD(v15[4]) = 0x1000000;
    v15[3] = &v13;
    LODWORD(v2) = RtlQueryRegistryValuesEx(
                    0,
                    L"\\Registry\\Machine\\System\\CurrentControlSet\\Enum\\HTREE\\ROOT\\0",
                    v15,
                    0,
                    0);
    LOBYTE(v3) = (_BYTE)v2;
    if ( (int)v2 < 0 )
      goto LABEL_12;
    LODWORD(v2) = IoGetDeviceProperty(
                    *(PDEVICE_OBJECT *)(a1 + 16),
                    DevicePropertyContainerID,
                    0x9Au,
                    PropertyBuffer,
                    &ResultLength);
    LOBYTE(v3) = (_BYTE)v2;
    if ( (int)v2 < 0 )
      goto LABEL_12;
    v9[0] = _wcsnicmp(PropertyBuffer, Str2, 0x4Du) != 0;
    LODWORD(v2) = RtlSetPortableOperatingSystem();
    v3 = (int)v2;
  }
  if ( !v9[0] )
    goto LABEL_11;
  v10 = 0;
  v11 = 1;
  memset(v15, 0, 0xA8u);
  LODWORD(v15[4]) = 0x4000000;
  LODWORD(v15[1]) = 288;
  v15[2] = L"Hibernate";
  LODWORD(v15[8]) = 288;
  v15[3] = &v10;
  LODWORD(v15[11]) = 0x4000000;
  v15[9] = L"Sleep";
  v15[10] = &v11;
  RegistryValues = RtlQueryRegistryValuesEx(
                     0,
                     L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Microsoft\\PortableOperatingSystem",
                     v15,
                     0,
                     0);
  if ( v3 >= 0 )
    v3 = RegistryValues;
  v5 = v10 == 0 ? 8 : 0;
  LODWORD(v2) = -v11;
  if ( !(v5 | (v11 == 0 ? 7 : 0)) )
  {
LABEL_11:
    if ( v3 >= 0 )
      return (int)v2;
    goto LABEL_12;
  }
  LODWORD(v2) = PoDisableSleepStates(3, v5 | (unsigned int)(v11 == 0 ? 7 : 0), &v14);
  if ( v3 >= 0 )
  {
    v3 = (int)v2;
    goto LABEL_11;
  }
LABEL_12:
  if ( gTracingEnabled )
  {
    v2 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v7) = 2;
      LODWORD(v2) = WPP_RECORDER_SF_d(Default, v7, 1, 19, (__int64)WPP_36185c522d943f8d0ee1935152861c3e_Traceguids, v3);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x140005490  push    rbp
0x140005492  push    rbx
0x140005493  push    rdi
0x140005494  push    r14
0x140005496  lea     rbp, [rsp-168h]
0x14000549e  sub     rsp, 268h
0x1400054a5  mov     rax, cs:__security_cookie
0x1400054ac  xor     rax, rsp
0x1400054af  mov     [rbp+180h+var_30], rax
0x1400054b6  mov     rdi, rcx
0x1400054b9  mov     [rsp+280h+var_248], 0
0x1400054c1  mov     r14d, 9Ah
0x1400054c7  mov     [rsp+280h+var_24C], 0
0x1400054cf  mov     r8d, r14d; Size
0x1400054d2  mov     [rsp+280h+var_250], 0
0x1400054d7  xor     edx, edx; Val
0x1400054d9  lea     rcx, [rbp+180h+Str2]; void *
0x1400054dd  call    memset
0x1400054e2  xorps   xmm0, xmm0
0x1400054e5  mov     [rsp+280h+var_244], 0
0x1400054ed  lea     rcx, [rsp+280h+var_250]
0x1400054f2  mov     [rsp+280h+var_230], 0
0x1400054fb  movups  [rsp+280h+var_240], xmm0
0x140005500  call    cs:__imp_RtlCheckPortableOperatingSystem
0x140005507  nop     dword ptr [rax+rax+00h]
0x14000550c  mov     ebx, eax
0x14000550e  cmp     eax, 0C0000225h
0x140005513  jnz     loc_1400055F4
0x140005519  xor     edx, edx; Val
0x14000551b  lea     r8d, [r14+0Eh]; Size
0x14000551f  lea     rcx, [rsp+280h+var_220]; void *
0x140005524  call    memset
0x140005529  lea     rax, [rbp+180h+Str2]
0x14000552d  mov     dword ptr [rsp+280h+var_240], 9A0000h
0x140005535  mov     qword ptr [rsp+280h+var_240+8], rax
0x14000553a  lea     r8, [rsp+280h+var_220]
0x14000553f  lea     rax, aContainerid; "ContainerID"
0x140005546  mov     [rsp+280h+var_218], 124h
0x14000554e  mov     [rsp+280h+var_210], rax
0x140005553  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000555a  lea     rax, [rsp+280h+var_240]
0x14000555f  mov     [rbp+180h+var_200], 1000000h
0x140005566  xor     r9d, r9d
0x140005569  mov     [rsp+280h+var_208], rax
0x14000556e  xor     ecx, ecx
0x140005570  mov     [rsp+280h+ResultLength], 0
0x140005579  call    cs:__imp_RtlQueryRegistryValuesEx
0x140005580  nop     dword ptr [rax+rax+00h]
0x140005585  mov     ebx, eax
0x140005587  test    eax, eax
0x140005589  js      loc_1400056CB
0x14000558f  mov     rcx, [rdi+10h]; DeviceObject
0x140005593  lea     rax, [rsp+280h+var_244]
0x140005598  lea     r9, [rbp+180h+PropertyBuffer]; PropertyBuffer
0x14000559f  mov     [rsp+280h+ResultLength], rax; ResultLength
0x1400055a4  mov     r8d, r14d; BufferLength
0x1400055a7  mov     edx, 16h; DeviceProperty
0x1400055ac  call    cs:__imp_IoGetDeviceProperty
0x1400055b3  nop     dword ptr [rax+rax+00h]
0x1400055b8  mov     ebx, eax
0x1400055ba  test    eax, eax
0x1400055bc  js      loc_1400056CB
0x1400055c2  lea     r8d, [r14-4Dh]; MaxCount
0x1400055c6  lea     rdx, [rbp+180h+Str2]; Str2
0x1400055ca  lea     rcx, [rbp+180h+PropertyBuffer]; Str1
0x1400055d1  call    cs:__imp__wcsnicmp
0x1400055d8  nop     dword ptr [rax+rax+00h]
0x1400055dd  test    eax, eax
0x1400055df  setnz   cl
0x1400055e2  mov     [rsp+280h+var_250], cl
0x1400055e6  call    cs:__imp_RtlSetPortableOperatingSystem
0x1400055ed  nop     dword ptr [rax+rax+00h]
0x1400055f2  mov     ebx, eax
0x1400055f4  cmp     [rsp+280h+var_250], 0
0x1400055f9  jz      loc_1400056C7
0x1400055ff  xor     edx, edx; Val
0x140005601  mov     [rsp+280h+var_24C], 0
0x140005609  mov     r8d, 0A8h; Size
0x14000560f  mov     [rsp+280h+var_248], 1
0x140005617  lea     rcx, [rsp+280h+var_220]; void *
0x14000561c  call    memset
0x140005621  mov     ecx, 4000000h
0x140005626  mov     [rsp+280h+ResultLength], 0
0x14000562f  mov     edx, 120h
0x140005634  mov     [rbp+180h+var_200], ecx
0x140005637  lea     rax, aHibernate; "Hibernate"
0x14000563e  mov     [rsp+280h+var_218], edx
0x140005642  mov     [rsp+280h+var_210], rax
0x140005647  lea     r8, [rsp+280h+var_220]
0x14000564c  lea     rax, [rsp+280h+var_24C]
0x140005651  mov     [rbp+180h+var_1E0], edx
0x140005654  mov     [rsp+280h+var_208], rax
0x140005659  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140005660  lea     rax, aSleep; "Sleep"
0x140005667  mov     [rbp+180h+var_1C8], ecx
0x14000566a  mov     [rbp+180h+var_1D8], rax
0x14000566e  xor     r9d, r9d
0x140005671  lea     rax, [rsp+280h+var_248]
0x140005676  xor     ecx, ecx
0x140005678  mov     [rbp+180h+var_1D0], rax
0x14000567c  call    cs:__imp_RtlQueryRegistryValuesEx
0x140005683  nop     dword ptr [rax+rax+00h]
0x140005688  test    ebx, ebx
0x14000568a  cmovns  ebx, eax
0x14000568d  mov     eax, [rsp+280h+var_24C]
0x140005691  neg     eax
0x140005693  mov     eax, [rsp+280h+var_248]
0x140005697  sbb     ecx, ecx
0x140005699  not     ecx
0x14000569b  and     ecx, 8
0x14000569e  neg     eax
0x1400056a0  sbb     edx, edx
0x1400056a2  not     edx
0x1400056a4  and     edx, 7
0x1400056a7  or      edx, ecx
0x1400056a9  jz      short loc_1400056C7
0x1400056ab  lea     r8, [rsp+280h+var_230]
0x1400056b0  mov     ecx, 3
0x1400056b5  call    cs:__imp_PoDisableSleepStates
0x1400056bc  nop     dword ptr [rax+rax+00h]
0x1400056c1  test    ebx, ebx
0x1400056c3  js      short loc_1400056CB
0x1400056c5  mov     ebx, eax
0x1400056c7  test    ebx, ebx
0x1400056c9  jns     short loc_14000571E
0x1400056cb  cmp     cs:gTracingEnabled, 0
0x1400056d2  jz      short loc_14000571E
0x1400056d4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400056db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400056e2  jz      short loc_14000571E
0x1400056e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400056eb  mov     edi, 13h
0x1400056f0  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400056f7  nop     dword ptr [rax+rax+00h]
0x1400056fc  mov     [rsp+280h+var_258], ebx
0x140005700  lea     r8d, [rdi-12h]
0x140005704  mov     rcx, rax
0x140005707  movzx   r9d, di
0x14000570b  lea     rax, WPP_36185c522d943f8d0ee1935152861c3e_Traceguids
0x140005712  mov     dl, 2
0x140005714  mov     [rsp+280h+ResultLength], rax
0x140005719  call    WPP_RECORDER_SF_d
0x14000571e  mov     rcx, [rbp+180h+var_30]
0x140005725  xor     rcx, rsp; StackCookie
0x140005728  call    __security_check_cookie
0x14000572d  add     rsp, 268h
0x140005734  pop     r14
0x140005736  pop     rdi
0x140005737  pop     rbx
0x140005738  pop     rbp
0x140005739  retn
```
