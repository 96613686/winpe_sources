# uus::UndockedUpdateCoreTelemetry::FailoverVersionExcluded(UusVersion const &,bool,bool,char const *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18003e358`
- end: `0x18003e50b`
- name: `?FailoverVersionExcluded@UndockedUpdateCoreTelemetry@uus@@CAXAEBVUusVersion@@_N1PEBDV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `435`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18003e2f4`
- `0x18003e328`
- `0x18003e514`

## callees

- `0x18000109c`
- `0x1800089f4`
- `0x1800097d8`
- `0x180029644`
- `0x18003e358`
- `0x1800427d0`

## pseudocode

```c
__int64 __fastcall uus::UndockedUpdateCoreTelemetry::FailoverVersionExcluded(
        __int64 a1,
        char a2,
        char a3,
        const wchar_t *a4,
        __int64 *a5)
{
  __int64 v9; // r14
  int v10; // edi
  __int64 result; // rax
  __int64 v12; // rsi
  unsigned __int16 v13; // di
  __int64 String; // rax
  const wchar_t *v15; // rcx
  int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // edx
  char v20; // [rsp+38h] [rbp-A1h] BYREF
  char v21; // [rsp+39h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-99h] BYREF
  _BYTE v23[32]; // [rsp+48h] [rbp-91h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+68h] [rbp-71h] BYREF
  __int64 *v25; // [rsp+88h] [rbp-51h]
  __int64 v26; // [rsp+90h] [rbp-49h]
  const wchar_t *v27; // [rsp+98h] [rbp-41h]
  int v28; // [rsp+A0h] [rbp-39h]
  int v29; // [rsp+A4h] [rbp-35h]
  char *v30; // [rsp+A8h] [rbp-31h]
  __int64 v31; // [rsp+B0h] [rbp-29h]
  char *v32; // [rsp+B8h] [rbp-21h]
  __int64 v33; // [rsp+C0h] [rbp-19h]
  const wchar_t *v34; // [rsp+C8h] [rbp-11h]
  int v35; // [rsp+D0h] [rbp-9h]
  int v36; // [rsp+D4h] [rbp-5h]
  _DWORD *v37; // [rsp+D8h] [rbp-1h]
  __int64 v38; // [rsp+E0h] [rbp+7h]
  __int64 v39; // [rsp+E8h] [rbp+Fh]
  _DWORD v40[2]; // [rsp+F0h] [rbp+17h] BYREF

  v9 = *a5;
  v10 = *((_DWORD *)a5 + 2);
  result = (__int64)uus::UndockedUpdateCoreTelemetry::Provider();
  v12 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = 0x800000000000LL;
    if ( (*(_QWORD *)(v12 + 16) & 0x800000000000LL) != 0
      && (*(_QWORD *)(v12 + 24) & 0x800000000000LL) == *(_QWORD *)(v12 + 24) )
    {
      v20 = a3;
      v21 = a2;
      v13 = 2 * v10;
      String = UusVersion::GetString(a1, v23);
      v15 = (const wchar_t *)String;
      if ( *(_QWORD *)(String + 24) > 7u )
        v15 = *(const wchar_t **)String;
      v22 = 0x1000000;
      v37 = v40;
      v16 = 2;
      v40[0] = v13;
      v17 = -1;
      v38 = 2;
      v39 = v9;
      v40[1] = 0;
      if ( a4 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_BYTE *)a4 + v18) );
        v19 = v18 + 1;
      }
      else
      {
        a4 = &Src;
        v19 = 1;
      }
      v35 = v19;
      v32 = &v20;
      v30 = &v21;
      v34 = a4;
      v36 = 0;
      v33 = 1;
      v31 = 1;
      if ( v15 )
      {
        do
          ++v17;
        while ( v15[v17] );
        v16 = 2 * v17 + 2;
      }
      else
      {
        v15 = &qword_180050DC0;
      }
      v27 = v15;
      v25 = &v22;
      v28 = v16;
      v29 = 0;
      v26 = 8;
      tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)&dword_180057584, 0, 0, 9u, &v24);
      return std::wstring::_Tidy_deallocate(v23);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003e358  mov     rax, rsp
0x18003e35b  mov     [rax+10h], rbx
0x18003e35f  mov     [rax+18h], rsi
0x18003e363  mov     [rax+20h], rdi
0x18003e367  push    rbp
0x18003e368  push    r12
0x18003e36a  push    r13
0x18003e36c  push    r14
0x18003e36e  push    r15
0x18003e370  lea     rbp, [rax-57h]
0x18003e374  sub     rsp, 100h
0x18003e37b  mov     rax, cs:__security_cookie
0x18003e382  xor     rax, rsp
0x18003e385  mov     [rbp+4Fh+var_30], rax
0x18003e389  mov     rax, [rbp+4Fh+arg_20]
0x18003e38d  mov     rbx, r9
0x18003e390  mov     r15b, r8b
0x18003e393  mov     r12b, dl
0x18003e396  mov     r13, rcx
0x18003e399  mov     r14, [rax]
0x18003e39c  mov     edi, [rax+8]
0x18003e39f  call    ?Provider@UndockedUpdateCoreTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateCoreTelemetry::Provider(void)
0x18003e3a4  mov     rsi, rax
0x18003e3a7  cmp     dword ptr [rax], 5
0x18003e3aa  jbe     loc_18003E4DE
0x18003e3b0  mov     rax, 800000000000h
0x18003e3ba  test    [rsi+10h], rax
0x18003e3be  jz      loc_18003E4DE
0x18003e3c4  mov     rdx, [rsi+18h]
0x18003e3c8  and     rdx, rax
0x18003e3cb  cmp     rdx, [rsi+18h]
0x18003e3cf  jnz     loc_18003E4DE
0x18003e3d5  lea     rdx, [rsp+120h+var_E0]
0x18003e3da  mov     byte ptr [rsp+120h+var_F0], r15b
0x18003e3df  mov     rcx, r13
0x18003e3e2  mov     byte ptr [rsp+120h+var_F0+1], r12b
0x18003e3e7  add     di, di
0x18003e3ea  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003e3ef  mov     rcx, rax
0x18003e3f2  cmp     qword ptr [rax+18h], 7
0x18003e3f7  jbe     short loc_18003E3FC
0x18003e3f9  mov     rcx, [rax]
0x18003e3fc  lea     rax, [rbp+4Fh+var_38]
0x18003e400  mov     [rsp+120h+var_E8], 1000000h
0x18003e409  mov     [rbp+4Fh+var_50], rax
0x18003e40d  mov     r8d, 2
0x18003e413  movzx   eax, di
0x18003e416  xor     r9d, r9d; int
0x18003e419  mov     [rbp+4Fh+var_38], eax
0x18003e41c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e420  mov     [rbp+4Fh+var_48], r8
0x18003e424  mov     [rbp+4Fh+var_40], r14
0x18003e428  lea     r10d, [r8-1]
0x18003e42c  mov     [rbp+4Fh+var_34], r9d
0x18003e430  test    rbx, rbx
0x18003e433  jz      short loc_18003E445
0x18003e435  mov     rdx, rax
0x18003e438  inc     rdx
0x18003e43b  cmp     [rbx+rdx], r9b
0x18003e43f  jnz     short loc_18003E438
0x18003e441  inc     edx
0x18003e443  jmp     short loc_18003E44F
0x18003e445  lea     rbx, Src
0x18003e44c  mov     edx, r10d
0x18003e44f  mov     [rbp+4Fh+var_58], edx
0x18003e452  lea     rdx, [rsp+120h+var_F0]
0x18003e457  mov     [rbp+4Fh+var_70], rdx
0x18003e45b  lea     rdx, [rsp+120h+var_F0+1]
0x18003e460  mov     [rbp+4Fh+var_80], rdx
0x18003e464  mov     [rbp+4Fh+var_60], rbx
0x18003e468  mov     [rbp+4Fh+var_54], r9d
0x18003e46c  mov     [rbp+4Fh+var_68], r10
0x18003e470  mov     [rbp+4Fh+var_78], r10
0x18003e474  test    rcx, rcx
0x18003e477  jz      short loc_18003E48D
0x18003e479  inc     rax
0x18003e47c  cmp     [rcx+rax*2], r9w
0x18003e481  jnz     short loc_18003E479
0x18003e483  lea     r8d, ds:2[rax*2]
0x18003e48b  jmp     short loc_18003E494
0x18003e48d  lea     rcx, qword_180050DC0
0x18003e494  lea     rax, [rsp+120h+var_E8]
0x18003e499  mov     [rbp+4Fh+var_90], rcx
0x18003e49d  mov     [rbp+4Fh+var_A0], rax
0x18003e4a1  lea     rdx, dword_180057584; int
0x18003e4a8  lea     rax, [rbp+4Fh+var_C0]
0x18003e4ac  mov     [rbp+4Fh+var_88], r8d
0x18003e4b0  mov     [rsp+120h+var_F8], rax; PEVENT_DATA_DESCRIPTOR
0x18003e4b5  xor     r8d, r8d; int
0x18003e4b8  mov     rcx, rsi; int
0x18003e4bb  mov     [rsp+120h+var_100], 9; ULONG
0x18003e4c3  mov     [rbp+4Fh+var_84], r9d
0x18003e4c7  mov     [rbp+4Fh+var_98], 8
0x18003e4cf  call    _tlgWriteTransfer_EventWriteTransfer
0x18003e4d4  lea     rcx, [rsp+120h+var_E0]
0x18003e4d9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e4de  mov     rcx, [rbp+4Fh+var_30]
0x18003e4e2  xor     rcx, rsp; StackCookie
0x18003e4e5  call    __security_check_cookie
0x18003e4ea  lea     r11, [rsp+120h+var_20]
0x18003e4f2  mov     rbx, [r11+38h]
0x18003e4f6  mov     rsi, [r11+40h]
0x18003e4fa  mov     rdi, [r11+48h]
0x18003e4fe  mov     rsp, r11
0x18003e501  pop     r15
0x18003e503  pop     r14
0x18003e505  pop     r13
0x18003e507  pop     r12
0x18003e509  pop     rbp
0x18003e50a  retn
```
