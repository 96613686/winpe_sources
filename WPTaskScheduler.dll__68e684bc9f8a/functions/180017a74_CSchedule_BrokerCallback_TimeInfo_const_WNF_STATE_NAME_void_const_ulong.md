# CSchedule::BrokerCallback(TimeInfo const &,_WNF_STATE_NAME *,void * const,ulong)

- ea: `0x180017a74`
- end: `0x180017bfe`
- name: `?BrokerCallback@CSchedule@@QEAAJAEBVTimeInfo@@PEAU_WNF_STATE_NAME@@QEAXK@Z`
- size: `394`
- prototype: `__int64 __fastcall(struct _GUID *this, const struct TimeInfo *, struct _WNF_STATE_NAME *, void *const)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800188cc`

## callees

- `0x18000d290`
- `0x18000d460`
- `0x18000ea40`
- `0x18000f760`
- `0x180017a74`
- `0x18001f65c`
- `0x18001f87c`
- `0x180020c30`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CSchedule::BrokerCallback(
        struct _GUID *this,
        const struct TimeInfo *a2,
        struct _WNF_STATE_NAME *a3,
        void *const a4)
{
  __int64 v6; // r10
  __int64 v7; // r11
  int v8; // ebx
  void (__fastcall ***v9)(_QWORD, _BYTE *); // rcx
  _BYTE v11[48]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v12[16]; // [rsp+60h] [rbp-38h] BYREF

  if ( *(_QWORD *)this[12].Data4 && *(_QWORD *)this[13].Data4 )
  {
    CSchedule::GetTimeInFormat(this, v11, a2, a4);
    v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v6 + 128LL))(v6, v11, v7);
    if ( (this[2].Data4[4] & 2) == 0
      && !*(_DWORD *)this[16].Data4
      && (unsigned int)CSchedule::IsWithinInterval((CSchedule *)this, (const struct TimeValue *)v11)
      && *(_DWORD *)this[2].Data4 == 4
      && v8 )
    {
      v9 = *(void (__fastcall ****)(_QWORD, _BYTE *))this[13].Data4;
      ++this[9].Data1;
      (**v9)(v9, v11);
      (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)this[12].Data4 + 72LL))(*(_QWORD *)this[12].Data4, v11);
      (*(void (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)this[12].Data4 + 96LL))(
        *(_QWORD *)this[12].Data4,
        v11,
        1);
      if ( (this[2].Data4[4] & 1) != 0 )
      {
        TaskStore::PersistStatistics(qword_180030AC8, this + 1);
        TaskStore::PersistRuntimeData(qword_180030AC8, this + 1, 1);
      }
      if ( !*(_DWORD *)this[16].Data4 )
        CSchedule::UpdateState((CSchedule *)this, a2);
    }
    return 0;
  }
  else
  {
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(this, ErrorNullPointer, a3, 1, v12);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180017a74  push    rbx
0x180017a76  push    rsi
0x180017a77  push    rdi
0x180017a78  sub     rsp, 80h
0x180017a7f  mov     rax, cs:__security_cookie
0x180017a86  xor     rax, rsp
0x180017a89  mov     [rsp+98h+var_28], rax
0x180017a8e  mov     r10, [rcx+0C8h]
0x180017a95  mov     r11, r8
0x180017a98  mov     rsi, rdx
0x180017a9b  mov     rdi, rcx
0x180017a9e  test    r10, r10
0x180017aa1  jz      loc_180017BBC
0x180017aa7  cmp     qword ptr [rcx+0D8h], 0
0x180017aaf  jz      loc_180017BBC
0x180017ab5  mov     r8, rdx
0x180017ab8  lea     rdx, [rsp+98h+var_68]
0x180017abd  call    ?GetTimeInFormat@CSchedule@@AEAA?AVTimeValue@@AEBVTimeInfo@@@Z; CSchedule::GetTimeInFormat(TimeInfo const &)
0x180017ac2  mov     rcx, [r10]
0x180017ac5  lea     rdx, [rsp+98h+var_68]
0x180017aca  mov     r8, r11
0x180017acd  mov     rax, [rcx+80h]
0x180017ad4  mov     ecx, [rsp+98h+arg_20]
0x180017adb  mov     dword ptr [rsp+98h+var_78], ecx
0x180017adf  mov     rcx, r10
0x180017ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ae7  test    byte ptr [rdi+2Ch], 2
0x180017aeb  mov     ebx, eax
0x180017aed  jnz     loc_180017BB8
0x180017af3  cmp     dword ptr [rdi+108h], 0
0x180017afa  jnz     loc_180017BB8
0x180017b00  lea     rdx, [rsp+98h+var_68]; struct TimeValue *
0x180017b05  mov     rcx, rdi; this
0x180017b08  call    ?IsWithinInterval@CSchedule@@AEAAHAEBVTimeValue@@@Z; CSchedule::IsWithinInterval(TimeValue const &)
0x180017b0d  test    eax, eax
0x180017b0f  jz      loc_180017BB8
0x180017b15  cmp     dword ptr [rdi+28h], 4
0x180017b19  jnz     loc_180017BB8
0x180017b1f  test    ebx, ebx
0x180017b21  jz      loc_180017BB8
0x180017b27  mov     rcx, [rdi+0D8h]
0x180017b2e  lea     rdx, [rsp+98h+var_68]
0x180017b33  inc     dword ptr [rdi+90h]
0x180017b39  mov     rax, [rcx]
0x180017b3c  mov     rax, [rax]
0x180017b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b44  mov     rcx, [rdi+0C8h]
0x180017b4b  lea     rdx, [rsp+98h+var_68]
0x180017b50  mov     rax, [rcx]
0x180017b53  mov     rax, [rax+48h]
0x180017b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b5c  mov     rcx, [rdi+0C8h]
0x180017b63  lea     rdx, [rsp+98h+var_68]
0x180017b68  xor     r9d, r9d
0x180017b6b  mov     rax, [rcx]
0x180017b6e  lea     r8d, [r9+1]
0x180017b72  mov     rax, [rax+60h]
0x180017b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b7b  test    byte ptr [rdi+2Ch], 1
0x180017b7f  jz      short loc_180017BA4
0x180017b81  mov     rcx, cs:qword_180030AC8; this
0x180017b88  lea     rdx, [rdi+10h]; struct _GUID *
0x180017b8c  call    ?PersistStatistics@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::PersistStatistics(_GUID const &)
0x180017b91  mov     rcx, cs:qword_180030AC8; this
0x180017b98  lea     rdx, [rdi+10h]; struct _GUID *
0x180017b9c  mov     r8b, 1; bool
0x180017b9f  call    ?PersistRuntimeData@TaskStore@@QEAAJAEBU_GUID@@_N@Z; TaskStore::PersistRuntimeData(_GUID const &,bool)
0x180017ba4  cmp     dword ptr [rdi+108h], 0
0x180017bab  jnz     short loc_180017BB8
0x180017bad  mov     rdx, rsi; struct TimeInfo *
0x180017bb0  mov     rcx, rdi; this
0x180017bb3  call    ?UpdateState@CSchedule@@AEAAXAEBVTimeInfo@@@Z; CSchedule::UpdateState(TimeInfo const &)
0x180017bb8  xor     eax, eax
0x180017bba  jmp     short loc_180017BE6
0x180017bbc  test    cs:byte_180030D04, 1
0x180017bc3  jz      short loc_180017BE1
0x180017bc5  lea     rax, [rsp+98h+var_38]
0x180017bca  mov     r9d, 1
0x180017bd0  lea     rdx, ErrorNullPointer
0x180017bd7  mov     [rsp+98h+var_78], rax
0x180017bdc  call    McGenEventWrite_EventWriteTransfer
0x180017be1  mov     eax, 80004003h
0x180017be6  mov     rcx, [rsp+98h+var_28]
0x180017beb  xor     rcx, rsp; StackCookie
0x180017bee  call    __security_check_cookie
0x180017bf3  add     rsp, 80h
0x180017bfa  pop     rdi
0x180017bfb  pop     rsi
0x180017bfc  pop     rbx
0x180017bfd  retn
```
