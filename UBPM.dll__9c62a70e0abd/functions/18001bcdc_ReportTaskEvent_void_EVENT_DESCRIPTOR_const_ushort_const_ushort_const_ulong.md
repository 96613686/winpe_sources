# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong)

- ea: `0x18001bcdc`
- end: `0x18001bde8`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2K@Z`
- size: `268`
- prototype: `unsigned int(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180007000`
- `0x18000aff0`
- `0x180023b50`

## callees

- `0x180007e9c`
- `0x18001bcdc`
- `0x18001bdf0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001bd6d`
- `ntdll!EtwEventWrite` at `0x18001bd6d`
- `ntdll!EtwEventEnabled` at `0x18001bd1f`
- `ntdll!EtwEventEnabled` at `0x18001bd1f`

## string_xrefs

- `0x18001bd90`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18001bdc6`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        _QWORD *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        signed int a5)
{
  unsigned int v5; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  EventManager *v12; // rcx
  signed int v13; // ebx
  __int64 v14; // r8
  unsigned int v15; // r8d
  unsigned int v17; // [rsp+20h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+28h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v20; // [rsp+48h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-38h]

  v5 = a5;
  if ( a5 > 0 )
    v5 = (unsigned __int16)a5 | 0x80070000;
  v10 = *a1;
  v17 = v5;
  if ( v10 )
  {
    if ( (unsigned __int8)EtwEventEnabled(v10, a2)
      && (CreateDataDescriptor(&v18, a3),
          CreateDataDescriptor(&v19, a4),
          v21 = 4,
          v20 = &v17,
          v11 = EtwEventWrite(*a1, a2, 3, &v18),
          (v13 = v11) != 0) )
    {
      EventManager::LogIt(v12, L"EventWrite error", v11);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
  }
  else
  {
    v13 = 1;
  }
  v14 = (unsigned __int16)v13;
  if ( v13 >= 0 )
    v14 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v14);
  return v15;
}

```

## disassembly

```asm
0x18001bcdc  push    rbx
0x18001bcde  push    rbp
0x18001bcdf  push    rsi
0x18001bce0  push    rdi
0x18001bce1  sub     rsp, 68h
0x18001bce5  mov     rax, cs:__security_cookie
0x18001bcec  xor     rax, rsp
0x18001bcef  mov     [rsp+88h+var_30], rax
0x18001bcf4  mov     eax, [rsp+88h+arg_20]
0x18001bcfb  mov     rbp, r9
0x18001bcfe  mov     rsi, r8
0x18001bd01  mov     rdi, rdx
0x18001bd04  mov     rbx, rcx
0x18001bd07  test    eax, eax
0x18001bd09  jg      loc_18001BDB6
0x18001bd0f  mov     rcx, [rcx]
0x18001bd12  mov     [rsp+88h+var_68], eax
0x18001bd16  test    rcx, rcx
0x18001bd19  jz      loc_18001BDE1
0x18001bd1f  call    cs:__imp_EtwEventEnabled
0x18001bd26  nop     dword ptr [rax+rax+00h]
0x18001bd2b  test    al, al
0x18001bd2d  jz      short loc_18001BD7F
0x18001bd2f  mov     rdx, rsi; unsigned __int16 *
0x18001bd32  lea     rcx, [rsp+88h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bd37  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001bd3c  mov     rdx, rbp; unsigned __int16 *
0x18001bd3f  lea     rcx, [rsp+88h+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bd44  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001bd49  lea     rcx, [rsp+88h+var_68]
0x18001bd4e  mov     [rsp+88h+var_38], 4
0x18001bd57  mov     [rsp+88h+var_40], rcx
0x18001bd5c  lea     r9, [rsp+88h+var_60]
0x18001bd61  mov     rcx, [rbx]
0x18001bd64  mov     r8d, 3
0x18001bd6a  mov     rdx, rdi
0x18001bd6d  call    cs:__imp_EtwEventWrite
0x18001bd74  nop     dword ptr [rax+rax+00h]
0x18001bd79  mov     ebx, eax
0x18001bd7b  test    eax, eax
0x18001bd7d  jnz     short loc_18001BDC3
0x18001bd7f  xor     ebx, ebx
0x18001bd81  xor     ecx, ecx
0x18001bd83  movzx   r8d, bx
0x18001bd87  test    ebx, ebx
0x18001bd89  mov     rdx, rdi
0x18001bd8c  cmovns  r8d, ecx
0x18001bd90  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001bd97  call    TaskEventTrace
0x18001bd9c  mov     eax, r8d
0x18001bd9f  mov     rcx, [rsp+88h+var_30]
0x18001bda4  xor     rcx, rsp; StackCookie
0x18001bda7  call    __security_check_cookie
0x18001bdac  add     rsp, 68h
0x18001bdb0  pop     rdi
0x18001bdb1  pop     rsi
0x18001bdb2  pop     rbp
0x18001bdb3  pop     rbx
0x18001bdb4  retn
0x18001bdb6  movzx   eax, ax
0x18001bdb9  or      eax, 80070000h
0x18001bdbe  jmp     loc_18001BD0F
0x18001bdc3  mov     r8d, ebx; unsigned int
0x18001bdc6  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001bdcd  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001bdd2  test    ebx, ebx
0x18001bdd4  jle     short loc_18001BD81
0x18001bdd6  movzx   ebx, bx
0x18001bdd9  or      ebx, 80070000h
0x18001bddf  jmp     short loc_18001BD81
0x18001bde1  mov     ebx, 1
0x18001bde6  jmp     short loc_18001BD81
```
