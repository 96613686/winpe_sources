# uus::UndockedUpdateTelemetry::UusUnableToUpdateActiveVersion(UusVersion const &,bool,UusVersion const &,wchar_t const *)

- ea: `0x180009300`
- end: `0x1800094b6`
- name: `?UusUnableToUpdateActiveVersion@UndockedUpdateTelemetry@uus@@SAXAEBVUusVersion@@_N0PEB_W@Z`
- size: `438`
- prototype: `void __fastcall(const struct UusVersion *, bool, const struct UusVersion *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000e888`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x1800089f4`
- `0x180009300`
- `0x180029644`
- `0x1800427d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall uus::UndockedUpdateTelemetry::UusUnableToUpdateActiveVersion(
        const struct UusVersion *a1,
        char a2,
        const struct UusVersion *a3,
        const wchar_t *a4)
{
  const struct _tlgProvider_t *v8; // r15
  __int64 String; // rax
  const wchar_t *v10; // rbx
  const wchar_t *v11; // rax
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // edx
  __int64 v16; // rdx
  int v17; // edx
  char v18; // [rsp+30h] [rbp-99h] BYREF
  __int64 v19; // [rsp+38h] [rbp-91h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+80h] [rbp-49h] BYREF
  __int64 *v23; // [rsp+A0h] [rbp-29h]
  __int64 v24; // [rsp+A8h] [rbp-21h]
  const wchar_t *v25; // [rsp+B0h] [rbp-19h]
  int v26; // [rsp+B8h] [rbp-11h]
  int v27; // [rsp+BCh] [rbp-Dh]
  char *v28; // [rsp+C0h] [rbp-9h]
  __int64 v29; // [rsp+C8h] [rbp-1h]
  const wchar_t *v30; // [rsp+D0h] [rbp+7h]
  int v31; // [rsp+D8h] [rbp+Fh]
  int v32; // [rsp+DCh] [rbp+13h]
  const wchar_t *v33; // [rsp+E0h] [rbp+17h]
  int v34; // [rsp+E8h] [rbp+1Fh]
  int v35; // [rsp+ECh] [rbp+23h]

  v8 = uus::UndockedUpdateTelemetry::Provider();
  if ( *(_DWORD *)v8 > 5u
    && (*((_QWORD *)v8 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v8 + 3) & 0x200000000000LL) == *((_QWORD *)v8 + 3) )
  {
    String = UusVersion::GetString(a3, v21);
    v10 = (const wchar_t *)String;
    if ( *(_QWORD *)(String + 24) > 7u )
      v10 = *(const wchar_t **)String;
    v18 = a2;
    v11 = (const wchar_t *)UusVersion::GetString(a1, v20);
    if ( *((_QWORD *)v11 + 3) > 7u )
      v11 = *(const wchar_t **)v11;
    v19 = 0x2000000;
    v12 = 2;
    v13 = -1;
    if ( a4 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a4[v14] );
      v15 = 2 * v14 + 2;
    }
    else
    {
      a4 = &qword_180050DC0;
      v15 = 2;
    }
    v33 = a4;
    v34 = v15;
    v35 = 0;
    if ( v10 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v10[v16] );
      v17 = 2 * v16 + 2;
    }
    else
    {
      v10 = &qword_180050DC0;
      v17 = 2;
    }
    v30 = v10;
    v31 = v17;
    v32 = 0;
    v28 = &v18;
    v29 = 1;
    if ( v11 )
    {
      do
        ++v13;
      while ( v11[v13] );
      v12 = 2 * v13 + 2;
    }
    else
    {
      v11 = &qword_180050DC0;
    }
    v25 = v11;
    v26 = v12;
    v27 = 0;
    v23 = &v19;
    v24 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v8, (unsigned __int8 *)&byte_180056B19, 0, 0, 7u, &v22);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v21);
  }
}

```

## disassembly

```asm
0x180009300  mov     [rsp-8+arg_8], rbx
0x180009305  push    rbp
0x180009306  push    rsi
0x180009307  push    rdi
0x180009308  push    r14
0x18000930a  push    r15
0x18000930c  lea     rbp, [rsp-37h]
0x180009311  sub     rsp, 100h
0x180009318  mov     rax, cs:__security_cookie
0x18000931f  xor     rax, rsp
0x180009322  mov     [rbp+57h+var_30], rax
0x180009326  mov     rdi, r9
0x180009329  mov     rbx, r8
0x18000932c  mov     sil, dl
0x18000932f  mov     r14, rcx
0x180009332  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x180009337  mov     r15, rax
0x18000933a  cmp     dword ptr [rax], 5
0x18000933d  jbe     loc_180009493
0x180009343  mov     rax, 200000000000h
0x18000934d  test    [r15+10h], rax
0x180009351  jz      loc_180009493
0x180009357  mov     rcx, [r15+18h]
0x18000935b  and     rcx, rax
0x18000935e  cmp     rcx, [r15+18h]
0x180009362  jnz     loc_180009493
0x180009368  lea     rdx, [rbp+57h+var_C0]
0x18000936c  mov     rcx, rbx
0x18000936f  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180009374  mov     rbx, rax
0x180009377  cmp     qword ptr [rax+18h], 7
0x18000937c  jbe     short loc_180009381
0x18000937e  mov     rbx, [rax]
0x180009381  mov     [rsp+120h+var_F0], sil
0x180009386  lea     rdx, [rsp+120h+var_E0]
0x18000938b  mov     rcx, r14
0x18000938e  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180009393  cmp     qword ptr [rax+18h], 7
0x180009398  jbe     short loc_18000939D
0x18000939a  mov     rax, [rax]
0x18000939d  mov     [rsp+120h+var_E8], 2000000h
0x1800093a6  lea     r10, qword_180050DC0
0x1800093ad  mov     r8d, 2
0x1800093b3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800093b7  xor     r9d, r9d; int
0x1800093ba  test    rdi, rdi
0x1800093bd  jz      short loc_1800093D5
0x1800093bf  mov     rdx, rcx
0x1800093c2  inc     rdx
0x1800093c5  cmp     [rdi+rdx*2], r9w
0x1800093ca  jnz     short loc_1800093C2
0x1800093cc  lea     edx, ds:2[rdx*2]
0x1800093d3  jmp     short loc_1800093DB
0x1800093d5  mov     rdi, r10
0x1800093d8  mov     edx, r8d
0x1800093db  mov     [rbp+57h+var_40], rdi
0x1800093df  mov     [rbp+57h+var_38], edx
0x1800093e2  mov     [rbp+57h+var_34], r9d
0x1800093e6  test    rbx, rbx
0x1800093e9  jz      short loc_180009401
0x1800093eb  mov     rdx, rcx
0x1800093ee  inc     rdx
0x1800093f1  cmp     [rbx+rdx*2], r9w
0x1800093f6  jnz     short loc_1800093EE
0x1800093f8  lea     edx, ds:2[rdx*2]
0x1800093ff  jmp     short loc_180009407
0x180009401  mov     rbx, r10
0x180009404  mov     edx, r8d
0x180009407  mov     [rbp+57h+var_50], rbx
0x18000940b  mov     [rbp+57h+var_48], edx
0x18000940e  mov     [rbp+57h+var_44], r9d
0x180009412  lea     rdx, [rsp+120h+var_F0]
0x180009417  mov     [rbp+57h+var_60], rdx
0x18000941b  mov     [rbp+57h+var_58], 1
0x180009423  test    rax, rax
0x180009426  jz      short loc_18000943C
0x180009428  inc     rcx
0x18000942b  cmp     [rax+rcx*2], r9w
0x180009430  jnz     short loc_180009428
0x180009432  lea     r8d, ds:2[rcx*2]
0x18000943a  jmp     short loc_18000943F
0x18000943c  mov     rax, r10
0x18000943f  mov     [rbp+57h+var_70], rax
0x180009443  mov     [rbp+57h+var_68], r8d
0x180009447  mov     [rbp+57h+var_64], r9d
0x18000944b  lea     rax, [rsp+120h+var_E8]
0x180009450  mov     [rbp+57h+var_80], rax
0x180009454  mov     [rbp+57h+var_78], 8
0x18000945c  lea     rax, [rbp+57h+var_A0]
0x180009460  mov     [rsp+120h+var_F8], rax; PEVENT_DATA_DESCRIPTOR
0x180009465  mov     [rsp+120h+var_100], 7; ULONG
0x18000946d  xor     r8d, r8d; int
0x180009470  lea     rdx, byte_180056B19; int
0x180009477  mov     rcx, r15; int
0x18000947a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000947f  lea     rcx, [rsp+120h+var_E0]
0x180009484  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009489  nop
0x18000948a  lea     rcx, [rbp+57h+var_C0]
0x18000948e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009493  mov     rcx, [rbp+57h+var_30]
0x180009497  xor     rcx, rsp; StackCookie
0x18000949a  call    __security_check_cookie
0x18000949f  mov     rbx, [rsp+120h+arg_8]
0x1800094a7  add     rsp, 100h
0x1800094ae  pop     r15
0x1800094b0  pop     r14
0x1800094b2  pop     rdi
0x1800094b3  pop     rsi
0x1800094b4  pop     rbp
0x1800094b5  retn
```
