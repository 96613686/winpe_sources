# Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)

- ea: `0x14000732c`
- end: `0x14000755d`
- name: `?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z`
- size: `561`
- prototype: `__int64 *__fastcall(Windows::Speech::Session::FlightDataRecorder *, __int64 *, const CHAR *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003c64`
- `0x140004f38`
- `0x1400088c4`
- `0x14000c3d8`
- `0x14000d1f4`
- `0x14000fdf4`
- `0x1400180f0`

## callees

- `0x140002600`
- `0x1400036e8`
- `0x140003840`
- `0x140005ea0`
- `0x14000732c`
- `0x140007870`
- `0x14001bb90`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140007399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140007399`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400073e5`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400073e5`

## string_xrefs

- `0x140007392`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 *__fastcall Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(
        Windows::Speech::Session::FlightDataRecorder *a1,
        __int64 *a2,
        const CHAR *a3)
{
  int v6; // esi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  HSTRING v10; // r14
  __int64 v11; // rcx
  int v12; // r14d
  char v13; // al
  __int64 v14; // rcx
  __int64 *v15; // rcx
  __int64 v16; // rcx
  void (*v17)(void); // rax
  __int64 v18; // rcx
  __int64 *v20; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-48h]
  __int64 *v22[3]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF

  v22[1] = a2;
  *a2 = 0;
  v6 = 1;
  v21 = 1;
  if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(a1) < 0 )
    goto LABEL_11;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x14000755CLL);
  }
  v6 = 3;
  v21 = 3;
  v10 = string;
  v11 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  *a2 = 0;
  v20 = 0;
  v12 = RoActivateInstance(v10, &v20);
  if ( v12 >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = (__int64)v20;
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v20)(
              v20,
              &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
              a2);
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    }
  }
  if ( v12 < 0 )
LABEL_11:
    v13 = 0;
  else
    v13 = 1;
  if ( (v6 & 2) != 0 )
    v21 = v6 & 0xFFFFFFFD;
  if ( v13 )
  {
    v14 = *a2;
    v20 = (__int64 *)v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(
      (__int64)a1,
      (__int64 *)&v20,
      (__int64)L"eN",
      a3);
    v15 = (__int64 *)*a2;
    v20 = v15;
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64 *))(*v15 + 8))(v15);
      v15 = v20;
    }
    v22[2] = (__int64 *)&v20;
    v22[0] = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64 *))(*v15 + 8))(v15);
    Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(a1, v22, L"eT");
    v16 = (__int64)v20;
    if ( v20 )
    {
      v20 = 0;
      v17 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
LABEL_25:
      v17();
    }
  }
  else
  {
    v18 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      v17 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
      goto LABEL_25;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x14000732c  push    rbp
0x14000732e  push    rbx
0x14000732f  push    rsi
0x140007330  push    rdi
0x140007331  push    r12
0x140007333  push    r14
0x140007335  push    r15
0x140007337  mov     rbp, rsp
0x14000733a  sub     rsp, 70h
0x14000733e  mov     rax, cs:__security_cookie
0x140007345  xor     rax, rsp
0x140007348  mov     [rbp+var_8], rax
0x14000734c  mov     rdi, r9
0x14000734f  mov     r12, r8
0x140007352  mov     rbx, rdx
0x140007355  mov     r15, rcx
0x140007358  mov     [rbp+var_38], rdx
0x14000735c  mov     [rbp+var_48], 0
0x140007363  mov     qword ptr [rdx], 0
0x14000736a  mov     esi, 1
0x14000736f  mov     [rbp+var_48], esi
0x140007372  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140007377  test    eax, eax
0x140007379  js      loc_14000744A
0x14000737f  mov     [rbp+string], 0
0x140007387  lea     r9, [rbp+string]; string
0x14000738b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000738f  lea     edx, [rsi+1Bh]; length
0x140007392  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x140007399  call    cs:__imp_WindowsCreateStringReference
0x14000739f  test    eax, eax
0x1400073a1  js      loc_140007555
0x1400073a7  mov     esi, 3
0x1400073ac  mov     [rbp+var_48], esi
0x1400073af  mov     r14, [rbp+string]
0x1400073b3  mov     rcx, [rbx]
0x1400073b6  test    rcx, rcx
0x1400073b9  jz      short loc_1400073CF
0x1400073bb  mov     qword ptr [rbx], 0
0x1400073c2  mov     rax, [rcx]
0x1400073c5  mov     rax, [rax+10h]
0x1400073c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073ce  nop
0x1400073cf  mov     qword ptr [rbx], 0
0x1400073d6  mov     [rbp+var_50], 0
0x1400073de  lea     rdx, [rbp+var_50]
0x1400073e2  mov     rcx, r14
0x1400073e5  call    cs:__imp_RoActivateInstance
0x1400073eb  mov     r14d, eax
0x1400073ee  test    eax, eax
0x1400073f0  js      short loc_140007441
0x1400073f2  mov     r8d, 10h; Size
0x1400073f8  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1400073ff  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x140007406  call    memcmp_0
0x14000740b  mov     rcx, [rbp+var_50]
0x14000740f  test    eax, eax
0x140007411  jnz     short loc_140007418
0x140007413  mov     [rbx], rcx
0x140007416  jmp     short loc_140007441
0x140007418  mov     rax, [rcx]
0x14000741b  mov     r8, rbx
0x14000741e  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x140007425  mov     rax, [rax]
0x140007428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000742d  mov     r14d, eax
0x140007430  mov     rcx, [rbp+var_50]
0x140007434  mov     rax, [rcx]
0x140007437  mov     rax, [rax+10h]
0x14000743b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007440  nop
0x140007441  test    r14d, r14d
0x140007444  js      short loc_14000744A
0x140007446  mov     al, 1
0x140007448  jmp     short loc_14000744C
0x14000744a  xor     al, al
0x14000744c  test    sil, 2
0x140007450  jz      short loc_140007458
0x140007452  and     esi, 0FFFFFFFDh
0x140007455  mov     [rbp+var_48], esi
0x140007458  test    al, al
0x14000745a  jz      loc_14000751B
0x140007460  mov     rcx, [rbx]
0x140007463  mov     [rbp+var_50], rcx
0x140007467  test    rcx, rcx
0x14000746a  jz      short loc_140007479
0x14000746c  mov     rax, [rcx]
0x14000746f  mov     rax, [rax+8]
0x140007473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007478  nop
0x140007479  mov     r9, r12
0x14000747c  lea     r8, aEn; "eN"
0x140007483  lea     rdx, [rbp+var_50]
0x140007487  mov     rcx, r15
0x14000748a  call    ??$AddColumnToCoalescedEvent@PEBD@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGPEBD@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,char const *)
0x14000748f  mov     rcx, [rbx]
0x140007492  mov     [rbp+var_50], rcx
0x140007496  test    rcx, rcx
0x140007499  jz      short loc_1400074AB
0x14000749b  mov     rax, [rcx]
0x14000749e  mov     rax, [rax+8]
0x1400074a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074a7  mov     rcx, [rbp+var_50]
0x1400074ab  lea     rax, [rbp+var_50]
0x1400074af  mov     [rbp+var_30], rax
0x1400074b3  mov     [rbp+var_40], rcx
0x1400074b7  test    rcx, rcx
0x1400074ba  jz      short loc_1400074C9
0x1400074bc  mov     rax, [rcx]
0x1400074bf  mov     rax, [rax+8]
0x1400074c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074c8  nop
0x1400074c9  xorps   xmm3, xmm3
0x1400074cc  test    rdi, rdi
0x1400074cf  js      short loc_1400074D8
0x1400074d1  cvtsi2sd xmm3, rdi
0x1400074d6  jmp     short loc_1400074ED
0x1400074d8  mov     rax, rdi
0x1400074db  shr     rax, 1
0x1400074de  and     edi, 1
0x1400074e1  or      rax, rdi
0x1400074e4  cvtsi2sd xmm3, rax
0x1400074e9  addsd   xmm3, xmm3
0x1400074ed  lea     r8, aEt; "eT"
0x1400074f4  lea     rdx, [rbp+var_40]
0x1400074f8  mov     rcx, r15
0x1400074fb  call    ??$AddColumnToCoalescedEvent@N@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGN@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,double)
0x140007500  nop
0x140007501  mov     rcx, [rbp+var_50]
0x140007505  test    rcx, rcx
0x140007508  jz      short loc_140007537
0x14000750a  mov     [rbp+var_50], 0
0x140007512  mov     rax, [rcx]
0x140007515  mov     rax, [rax+10h]
0x140007519  jmp     short loc_140007531
0x14000751b  mov     rcx, [rbx]
0x14000751e  test    rcx, rcx
0x140007521  jz      short loc_140007537
0x140007523  mov     qword ptr [rbx], 0
0x14000752a  mov     rdx, [rcx]
0x14000752d  mov     rax, [rdx+10h]
0x140007531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007536  nop
0x140007537  mov     rax, rbx
0x14000753a  mov     rcx, [rbp+var_8]
0x14000753e  xor     rcx, rsp; StackCookie
0x140007541  call    __security_check_cookie
0x140007546  add     rsp, 70h
0x14000754a  pop     r15
0x14000754c  pop     r14
0x14000754e  pop     r12
0x140007550  pop     rdi
0x140007551  pop     rsi
0x140007552  pop     rbx
0x140007553  pop     rbp
0x140007554  retn
0x140007555  mov     ecx, eax; this
0x140007557  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
