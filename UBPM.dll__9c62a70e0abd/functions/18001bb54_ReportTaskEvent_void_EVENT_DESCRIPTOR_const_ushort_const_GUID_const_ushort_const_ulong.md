# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong)

- ea: `0x18001bb54`
- end: `0x18001bcd4`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2K@Z`
- size: `384`
- prototype: `unsigned int(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800060d0`
- `0x180007000`
- `0x180011a90`

## callees

- `0x180007e9c`
- `0x18001bb54`
- `0x18001bdf0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001bc08`
- `ntdll!EtwEventActivityIdControl` at `0x18001bc46`
- `ntdll!EtwEventActivityIdControl` at `0x18001bc08`
- `ntdll!EtwEventActivityIdControl` at `0x18001bc46`
- `ntdll!EtwEventWrite` at `0x18001bc21`
- `ntdll!EtwEventWrite` at `0x18001bc21`
- `ntdll!EtwEventEnabled` at `0x18001bba1`
- `ntdll!EtwEventEnabled` at `0x18001bba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc55`

## string_xrefs

- `0x18001bc76`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18001bcb9`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        char *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        signed int a6)
{
  unsigned int v6; // eax
  __int64 v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  int v13; // eax
  int v14; // edi
  EventManager *v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // r8d
  unsigned int v19; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v20[3]; // [rsp+28h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-39h] BYREF
  const struct _GUID *v22; // [rsp+50h] [rbp-29h]
  __int64 v23; // [rsp+58h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+60h] [rbp-19h] BYREF
  unsigned int *v25; // [rsp+70h] [rbp-9h]
  __int64 v26; // [rsp+78h] [rbp-1h]

  v6 = a6;
  if ( a6 > 0 )
    v6 = (unsigned __int16)a6 | 0x80070000;
  v11 = *(_QWORD *)a1;
  v19 = v6;
  if ( v11 )
  {
    if ( !(unsigned __int8)EtwEventEnabled(v11, a2) )
      goto LABEL_6;
    CreateDataDescriptor(&v21, a3);
    v22 = a4;
    v23 = 16;
    CreateDataDescriptor(&v24, a5);
    v25 = &v19;
    v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
    v26 = 4;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    EtwEventActivityIdControl(2, a4);
    v13 = EtwEventWrite(*(_QWORD *)a1, a2, 4, &v21);
    v20[0] = 0;
    v20[1] = 0;
    v14 = v13;
    EtwEventActivityIdControl(2, v20);
    LeaveCriticalSection(v12);
    if ( v14 )
    {
      EventManager::LogIt(v15, L"EventWrite error", v14);
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
LABEL_6:
      v14 = 0;
    }
  }
  else
  {
    v14 = 1;
  }
  v16 = (unsigned __int16)v14;
  if ( v14 >= 0 )
    v16 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v16);
  return v17;
}

```

## disassembly

```asm
0x18001bb54  push    rbp
0x18001bb56  push    rbx
0x18001bb57  push    rsi
0x18001bb58  push    rdi
0x18001bb59  push    r14
0x18001bb5b  push    r15
0x18001bb5d  lea     rbp, [rsp-1Fh]
0x18001bb62  sub     rsp, 98h
0x18001bb69  mov     rax, cs:__security_cookie
0x18001bb70  xor     rax, rsp
0x18001bb73  mov     [rbp+47h+var_40], rax
0x18001bb77  mov     eax, [rbp+47h+arg_28]
0x18001bb7a  mov     r14, r9
0x18001bb7d  mov     r15, [rbp+47h+arg_20]
0x18001bb81  mov     rbx, r8
0x18001bb84  mov     rsi, rdx
0x18001bb87  mov     rdi, rcx
0x18001bb8a  test    eax, eax
0x18001bb8c  jg      loc_18001BCA2
0x18001bb92  mov     rcx, [rcx]
0x18001bb95  mov     [rbp+47h+var_A0], eax
0x18001bb98  test    rcx, rcx
0x18001bb9b  jz      loc_18001BCAF
0x18001bba1  call    cs:__imp_EtwEventEnabled
0x18001bba8  nop     dword ptr [rax+rax+00h]
0x18001bbad  test    al, al
0x18001bbaf  jz      loc_18001BC65
0x18001bbb5  mov     rdx, rbx; unsigned __int16 *
0x18001bbb8  lea     rcx, [rbp+47h+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bbbc  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001bbc1  mov     rdx, r15; unsigned __int16 *
0x18001bbc4  mov     [rbp+47h+var_70], r14
0x18001bbc8  lea     rcx, [rbp+47h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bbcc  mov     [rbp+47h+var_68], 10h
0x18001bbd4  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001bbd9  lea     rcx, [rbp+47h+var_A0]
0x18001bbdd  mov     r15d, 4
0x18001bbe3  mov     [rbp+47h+var_50], rcx
0x18001bbe7  lea     rbx, [rdi+8]
0x18001bbeb  mov     rcx, rbx; lpCriticalSection
0x18001bbee  mov     [rbp+47h+var_48], r15
0x18001bbf2  call    cs:__imp_EnterCriticalSection
0x18001bbf9  nop     dword ptr [rax+rax+00h]
0x18001bbfe  mov     rdx, r14
0x18001bc01  lea     r14d, [r15-2]
0x18001bc05  mov     ecx, r14d
0x18001bc08  call    cs:__imp_EtwEventActivityIdControl
0x18001bc0f  nop     dword ptr [rax+rax+00h]
0x18001bc14  mov     rcx, [rdi]
0x18001bc17  lea     r9, [rbp+47h+var_80]
0x18001bc1b  mov     r8d, r15d
0x18001bc1e  mov     rdx, rsi
0x18001bc21  call    cs:__imp_EtwEventWrite
0x18001bc28  nop     dword ptr [rax+rax+00h]
0x18001bc2d  lea     rdx, [rbp+47h+var_98]
0x18001bc31  mov     [rbp+47h+var_98], 0
0x18001bc39  mov     ecx, r14d
0x18001bc3c  mov     [rbp+47h+var_90], 0
0x18001bc44  mov     edi, eax
0x18001bc46  call    cs:__imp_EtwEventActivityIdControl
0x18001bc4d  nop     dword ptr [rax+rax+00h]
0x18001bc52  mov     rcx, rbx; lpCriticalSection
0x18001bc55  call    cs:__imp_LeaveCriticalSection
0x18001bc5c  nop     dword ptr [rax+rax+00h]
0x18001bc61  test    edi, edi
0x18001bc63  jnz     short loc_18001BCB6
0x18001bc65  xor     edi, edi
0x18001bc67  xor     ecx, ecx
0x18001bc69  movzx   r8d, di
0x18001bc6d  test    edi, edi
0x18001bc6f  mov     rdx, rsi
0x18001bc72  cmovns  r8d, ecx
0x18001bc76  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001bc7d  call    TaskEventTrace
0x18001bc82  mov     eax, r8d
0x18001bc85  mov     rcx, [rbp+47h+var_40]
0x18001bc89  xor     rcx, rsp; StackCookie
0x18001bc8c  call    __security_check_cookie
0x18001bc91  add     rsp, 98h
0x18001bc98  pop     r15
0x18001bc9a  pop     r14
0x18001bc9c  pop     rdi
0x18001bc9d  pop     rsi
0x18001bc9e  pop     rbx
0x18001bc9f  pop     rbp
0x18001bca0  retn
0x18001bca2  movzx   eax, ax
0x18001bca5  or      eax, 80070000h
0x18001bcaa  jmp     loc_18001BB92
0x18001bcaf  mov     edi, 1
0x18001bcb4  jmp     short loc_18001BC67
0x18001bcb6  mov     r8d, edi; unsigned int
0x18001bcb9  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001bcc0  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001bcc5  test    edi, edi
0x18001bcc7  jle     short loc_18001BC67
0x18001bcc9  movzx   edi, di
0x18001bccc  or      edi, 80070000h
0x18001bcd2  jmp     short loc_18001BC67
```
