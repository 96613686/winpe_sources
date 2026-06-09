# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong)

- ea: `0x18001c87c`
- end: `0x18001ca7d`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2KK@Z`
- size: `513`
- prototype: `unsigned int __fastcall(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800060d0`
- `0x180011a90`

## callees

- `0x180007e9c`
- `0x18001c87c`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001c98b`
- `ntdll!EtwEventActivityIdControl` at `0x18001c9c6`
- `ntdll!EtwEventActivityIdControl` at `0x18001c98b`
- `ntdll!EtwEventActivityIdControl` at `0x18001c9c6`
- `ntdll!EtwEventWrite` at `0x18001c9a7`
- `ntdll!EtwEventWrite` at `0x18001c9a7`
- `ntdll!EtwEventEnabled` at `0x18001c8d4`
- `ntdll!EtwEventEnabled` at `0x18001c8d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c977`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c977`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c9d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c9d5`

## string_xrefs

- `0x18001c9f1`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18001ca40`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        char *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        signed int a6,
        unsigned int a7)
{
  unsigned int v8; // edx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  int v16; // eax
  int v17; // edi
  EventManager *v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r8d
  unsigned int v22; // [rsp+20h] [rbp-61h] BYREF
  unsigned int v23; // [rsp+28h] [rbp-59h] BYREF
  _QWORD v24[2]; // [rsp+30h] [rbp-51h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-41h] BYREF
  __int64 v26; // [rsp+48h] [rbp-39h]
  const struct _GUID *v27; // [rsp+50h] [rbp-31h]
  __int64 v28; // [rsp+58h] [rbp-29h]
  __int64 *v29; // [rsp+60h] [rbp-21h]
  __int64 v30; // [rsp+68h] [rbp-19h]
  unsigned int *v31; // [rsp+70h] [rbp-11h]
  __int64 v32; // [rsp+78h] [rbp-9h]
  unsigned int *v33; // [rsp+80h] [rbp-1h]
  __int64 v34; // [rsp+88h] [rbp+7h]

  v8 = a6;
  if ( a6 > 0 )
    v8 = (unsigned __int16)a6 | 0x80070000;
  v12 = *(_QWORD *)a1;
  v23 = a7;
  v22 = v8;
  if ( v12 )
  {
    if ( !(unsigned __int8)EtwEventEnabled(v12, a2) )
      goto LABEL_14;
    v13 = -1;
    if ( a3 )
    {
      v25 = (__int64 *)a3;
      v14 = -1;
      do
        ++v14;
      while ( a3[v14] );
      v26 = (unsigned int)(2 * v14 + 2);
    }
    else
    {
      v25 = &qword_1800439C0;
      v26 = 2;
    }
    v27 = a4;
    v28 = 16;
    if ( a5 )
    {
      v29 = (__int64 *)a5;
      do
        ++v13;
      while ( a5[v13] );
      v30 = (unsigned int)(2 * v13 + 2);
    }
    else
    {
      v29 = &qword_1800439C0;
      v30 = 2;
    }
    v32 = 4;
    v31 = &v22;
    v15 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
    v34 = 4;
    v33 = &v23;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    EtwEventActivityIdControl(2, a4);
    v16 = EtwEventWrite(*(_QWORD *)a1, a2, 5, &v25);
    v24[0] = 0;
    v24[1] = 0;
    v17 = v16;
    EtwEventActivityIdControl(2, v24);
    LeaveCriticalSection(v15);
    if ( v17 )
    {
      EventManager::LogIt(v18, L"EventWrite error", v17);
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
LABEL_14:
      v17 = 0;
    }
  }
  else
  {
    v17 = 1;
  }
  v19 = (unsigned __int16)v17;
  if ( v17 >= 0 )
    v19 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v19);
  return v20;
}

```

## disassembly

```asm
0x18001c87c  mov     [rsp-8+arg_10], rbx
0x18001c881  push    rbp
0x18001c882  push    rsi
0x18001c883  push    rdi
0x18001c884  push    r14
0x18001c886  push    r15
0x18001c888  lea     rbp, [rsp-1Fh]
0x18001c88d  sub     rsp, 0A0h
0x18001c894  mov     rax, cs:__security_cookie
0x18001c89b  xor     rax, rsp
0x18001c89e  mov     [rbp+3Fh+var_30], rax
0x18001c8a2  mov     rsi, rdx
0x18001c8a5  xor     r15d, r15d
0x18001c8a8  mov     edx, [rbp+3Fh+arg_28]
0x18001c8ab  mov     r14, r9
0x18001c8ae  mov     rbx, r8
0x18001c8b1  mov     rdi, rcx
0x18001c8b4  test    edx, edx
0x18001c8b6  jg      loc_18001CA2F
0x18001c8bc  mov     rcx, [rcx]
0x18001c8bf  mov     eax, [rbp+3Fh+arg_30]
0x18001c8c2  mov     [rbp+3Fh+var_98], eax
0x18001c8c5  mov     [rbp+3Fh+var_A0], edx
0x18001c8c8  test    rcx, rcx
0x18001c8cb  jz      loc_18001CA28
0x18001c8d1  mov     rdx, rsi
0x18001c8d4  call    cs:__imp_EtwEventEnabled
0x18001c8db  nop     dword ptr [rax+rax+00h]
0x18001c8e0  test    al, al
0x18001c8e2  jz      loc_18001C9E5
0x18001c8e8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c8ec  lea     rdx, qword_1800439C0
0x18001c8f3  test    rbx, rbx
0x18001c8f6  jz      loc_18001CA5B
0x18001c8fc  mov     [rbp+3Fh+var_80], rbx
0x18001c900  mov     rax, rcx
0x18001c903  inc     rax
0x18001c906  cmp     [rbx+rax*2], r15w
0x18001c90b  jnz     short loc_18001C903
0x18001c90d  lea     eax, ds:2[rax*2]
0x18001c914  mov     dword ptr [rbp+3Fh+var_78+4], r15d
0x18001c918  mov     dword ptr [rbp+3Fh+var_78], eax
0x18001c91b  mov     rax, [rbp+3Fh+arg_20]
0x18001c91f  mov     [rbp+3Fh+var_70], r14
0x18001c923  mov     [rbp+3Fh+var_68], 10h
0x18001c92b  test    rax, rax
0x18001c92e  jz      loc_18001CA6C
0x18001c934  mov     [rbp+3Fh+var_60], rax
0x18001c938  inc     rcx
0x18001c93b  cmp     [rax+rcx*2], r15w
0x18001c940  jnz     short loc_18001C938
0x18001c942  lea     eax, ds:2[rcx*2]
0x18001c949  mov     dword ptr [rbp+3Fh+var_58+4], r15d
0x18001c94d  mov     dword ptr [rbp+3Fh+var_58], eax
0x18001c950  lea     rax, [rbp+3Fh+var_A0]
0x18001c954  mov     [rbp+3Fh+var_48], 4
0x18001c95c  mov     [rbp+3Fh+var_50], rax
0x18001c960  lea     rbx, [rdi+8]
0x18001c964  lea     rax, [rbp+3Fh+var_98]
0x18001c968  mov     [rbp+3Fh+var_38], 4
0x18001c970  mov     rcx, rbx; lpCriticalSection
0x18001c973  mov     [rbp+3Fh+var_40], rax
0x18001c977  call    cs:__imp_EnterCriticalSection
0x18001c97e  nop     dword ptr [rax+rax+00h]
0x18001c983  mov     rdx, r14
0x18001c986  mov     ecx, 2
0x18001c98b  call    cs:__imp_EtwEventActivityIdControl
0x18001c992  nop     dword ptr [rax+rax+00h]
0x18001c997  mov     rcx, [rdi]
0x18001c99a  lea     r9, [rbp+3Fh+var_80]
0x18001c99e  mov     r8d, 5
0x18001c9a4  mov     rdx, rsi
0x18001c9a7  call    cs:__imp_EtwEventWrite
0x18001c9ae  nop     dword ptr [rax+rax+00h]
0x18001c9b3  lea     rdx, [rbp+3Fh+var_90]
0x18001c9b7  mov     [rbp+3Fh+var_90], r15
0x18001c9bb  mov     ecx, 2
0x18001c9c0  mov     [rbp+3Fh+var_88], r15
0x18001c9c4  mov     edi, eax
0x18001c9c6  call    cs:__imp_EtwEventActivityIdControl
0x18001c9cd  nop     dword ptr [rax+rax+00h]
0x18001c9d2  mov     rcx, rbx; lpCriticalSection
0x18001c9d5  call    cs:__imp_LeaveCriticalSection
0x18001c9dc  nop     dword ptr [rax+rax+00h]
0x18001c9e1  test    edi, edi
0x18001c9e3  jnz     short loc_18001CA3D
0x18001c9e5  mov     edi, r15d
0x18001c9e8  test    edi, edi
0x18001c9ea  movzx   r8d, di
0x18001c9ee  mov     rdx, rsi
0x18001c9f1  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001c9f8  cmovns  r8d, r15d
0x18001c9fc  call    TaskEventTrace
0x18001ca01  mov     eax, r8d
0x18001ca04  mov     rcx, [rbp+3Fh+var_30]
0x18001ca08  xor     rcx, rsp; StackCookie
0x18001ca0b  call    __security_check_cookie
0x18001ca10  mov     rbx, [rsp+0C0h+arg_10]
0x18001ca18  add     rsp, 0A0h
0x18001ca1f  pop     r15
0x18001ca21  pop     r14
0x18001ca23  pop     rdi
0x18001ca24  pop     rsi
0x18001ca25  pop     rbp
0x18001ca26  retn
0x18001ca28  mov     edi, 1
0x18001ca2d  jmp     short loc_18001C9E8
0x18001ca2f  movzx   edx, dx
0x18001ca32  or      edx, 80070000h
0x18001ca38  jmp     loc_18001C8BC
0x18001ca3d  mov     r8d, edi; unsigned int
0x18001ca40  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001ca47  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001ca4c  test    edi, edi
0x18001ca4e  jle     short loc_18001C9E8
0x18001ca50  movzx   edi, di
0x18001ca53  or      edi, 80070000h
0x18001ca59  jmp     short loc_18001C9E8
0x18001ca5b  mov     [rbp+3Fh+var_80], rdx
0x18001ca5f  mov     [rbp+3Fh+var_78], 2
0x18001ca67  jmp     loc_18001C91B
0x18001ca6c  mov     [rbp+3Fh+var_60], rdx
0x18001ca70  mov     [rbp+3Fh+var_58], 2
0x18001ca78  jmp     loc_18001C950
```
