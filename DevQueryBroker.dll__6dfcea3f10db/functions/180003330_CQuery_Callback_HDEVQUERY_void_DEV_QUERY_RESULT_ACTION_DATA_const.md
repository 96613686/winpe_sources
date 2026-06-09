# CQuery::Callback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x180003330`
- end: `0x18000344e`
- name: `?Callback@CQuery@@KAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `286`
- prototype: `void __fastcall(struct HDEVQUERY__ *, CQuery *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003330`
- `0x180003a64`
- `0x180003d14`
- `0x180003da4`
- `0x180003e50`

## import_xrefs

- `BrokerLib!BrSignalBrokerEvent2` at `0x1800033c2`
- `BrokerLib!BrSignalBrokerEvent2` at `0x1800033c2`

## pseudocode

```c
void __fastcall CQuery::Callback(struct HDEVQUERY__ *a1, CQuery *a2, const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  signed int v4; // eax
  bool v5; // sf
  int v6; // eax
  __int64 v7; // r8

  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 != 1 && (unsigned int)(*(_DWORD *)a3 - 2) >= 2 )
      goto LABEL_4;
    CQuery::InsertEvent(a2, a3, 0);
  }
  else
  {
    if ( *((_DWORD *)a3 + 2) != 1 )
    {
      if ( *((_DWORD *)a3 + 2) == 2 )
      {
        v4 = -2147467260;
LABEL_14:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, (unsigned int)v4, a2);
        CQuery::Stop(a2);
        v6 = CQuery::Start((struct _RTL_CRITICAL_SECTION *)a2);
        if ( v6 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v7, (unsigned int)v6, a2);
        }
        return;
      }
LABEL_4:
      v4 = -2147418113;
      goto LABEL_14;
    }
    *((_DWORD *)a2 + 34) = 1;
  }
  if ( *((_DWORD *)a2 + 34) )
  {
    v4 = BrSignalBrokerEvent2(
           *((_QWORD *)a2 + 18),
           *((_QWORD *)a2 + 19),
           0,
           &CLSID_RuntimeClass_Windows_Devices_Background_DeviceWatcherTriggerDetails,
           16,
           (char *)a2 + 48);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    if ( v5 )
      goto LABEL_14;
  }
}

```

## disassembly

```asm
0x180003330  mov     [rsp+arg_0], rbx
0x180003335  push    rdi
0x180003336  sub     rsp, 30h
0x18000333a  mov     ecx, [r8]
0x18000333d  mov     r9, r8
0x180003340  mov     rbx, rdx
0x180003343  test    ecx, ecx
0x180003345  jz      short loc_18000336D
0x180003347  sub     ecx, 1
0x18000334a  jz      short loc_18000335D
0x18000334c  sub     ecx, 1
0x18000334f  jz      short loc_18000335D
0x180003351  cmp     ecx, 1
0x180003354  jz      short loc_18000335D
0x180003356  mov     eax, 8000FFFFh
0x18000335b  jmp     short loc_1800033D8
0x18000335d  xor     r8d, r8d; int
0x180003360  mov     rdx, r9; struct _DEV_QUERY_RESULT_ACTION_DATA *
0x180003363  mov     rcx, rbx; this
0x180003366  call    ?InsertEvent@CQuery@@QEAAJPEBU_DEV_QUERY_RESULT_ACTION_DATA@@H@Z; CQuery::InsertEvent(_DEV_QUERY_RESULT_ACTION_DATA const *,int)
0x18000336b  jmp     short loc_18000338C
0x18000336d  mov     ecx, [r8+8]
0x180003371  sub     ecx, 1
0x180003374  jz      short loc_180003382
0x180003376  cmp     ecx, 1
0x180003379  jnz     short loc_180003356
0x18000337b  mov     eax, 80004004h
0x180003380  jmp     short loc_1800033D8
0x180003382  mov     dword ptr [rdx+88h], 1
0x18000338c  cmp     dword ptr [rbx+88h], 0
0x180003393  jz      loc_180003443
0x180003399  mov     rdx, [rbx+98h]
0x1800033a0  lea     rax, [rbx+30h]
0x1800033a4  mov     rcx, [rbx+90h]
0x1800033ab  lea     r9, CLSID_RuntimeClass_Windows_Devices_Background_DeviceWatcherTriggerDetails
0x1800033b2  mov     [rsp+38h+var_10], rax
0x1800033b7  xor     r8d, r8d
0x1800033ba  mov     dword ptr [rsp+38h+var_18], 10h
0x1800033c2  call    cs:__imp_BrSignalBrokerEvent2
0x1800033c8  test    eax, eax
0x1800033ca  jle     short loc_1800033D6
0x1800033cc  movzx   eax, ax
0x1800033cf  or      eax, 80070000h
0x1800033d4  test    eax, eax
0x1800033d6  jns     short loc_180003443
0x1800033d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033df  lea     rdi, WPP_GLOBAL_Control
0x1800033e6  cmp     rcx, rdi
0x1800033e9  jz      short loc_180003407
0x1800033eb  cmp     byte ptr [rcx+19h], 2
0x1800033ef  jb      short loc_180003407
0x1800033f1  mov     rcx, [rcx+10h]
0x1800033f5  mov     edx, 0Ah
0x1800033fa  mov     r9d, eax
0x1800033fd  mov     [rsp+38h+var_18], rbx
0x180003402  call    WPP_SF_Dq
0x180003407  mov     rcx, rbx; this
0x18000340a  call    ?Stop@CQuery@@QEAAXXZ; CQuery::Stop(void)
0x18000340f  mov     rcx, rbx; this
0x180003412  call    ?Start@CQuery@@QEAAJXZ; CQuery::Start(void)
0x180003417  test    eax, eax
0x180003419  jns     short loc_180003443
0x18000341b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003422  cmp     rcx, rdi
0x180003425  jz      short loc_180003443
0x180003427  cmp     byte ptr [rcx+19h], 2
0x18000342b  jb      short loc_180003443
0x18000342d  mov     rcx, [rcx+10h]
0x180003431  mov     edx, 0Bh
0x180003436  mov     r9d, eax
0x180003439  mov     [rsp+38h+var_18], rbx
0x18000343e  call    WPP_SF_Dq
0x180003443  mov     rbx, [rsp+38h+arg_0]
0x180003448  add     rsp, 30h
0x18000344c  pop     rdi
0x18000344d  retn
```
