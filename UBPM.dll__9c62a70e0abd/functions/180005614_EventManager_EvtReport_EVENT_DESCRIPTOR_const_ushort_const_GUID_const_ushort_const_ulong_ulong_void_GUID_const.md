# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong,void *,_GUID const *)

- ea: `0x180005614`
- end: `0x1800057d5`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1KKPEAX2@Z`
- size: `449`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, char, char, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800060d0`
- `0x180011a90`

## callees

- `0x180005614`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180005709`
- `ntdll!EtwEventActivityIdControl` at `0x180005744`
- `ntdll!EtwEventActivityIdControl` at `0x180005709`
- `ntdll!EtwEventActivityIdControl` at `0x180005744`
- `ntdll!EtwEventWrite` at `0x180005725`
- `ntdll!EtwEventWrite` at `0x180005725`
- `ntdll!EtwEventEnabled` at `0x180005655`
- `ntdll!EtwEventEnabled` at `0x180005655`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005754`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005754`

## string_xrefs

- `0x180005794`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        char a6,
        char a7)
{
  __int64 v8; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  signed int v14; // eax
  signed int v15; // edi
  EventManager *v16; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-61h] BYREF
  __int64 *v19; // [rsp+30h] [rbp-51h] BYREF
  __int64 v20; // [rsp+38h] [rbp-49h]
  const struct _GUID *v21; // [rsp+40h] [rbp-41h]
  __int64 v22; // [rsp+48h] [rbp-39h]
  __int64 *v23; // [rsp+50h] [rbp-31h]
  __int64 v24; // [rsp+58h] [rbp-29h]
  char *v25; // [rsp+60h] [rbp-21h]
  __int64 v26; // [rsp+68h] [rbp-19h]
  char *v27; // [rsp+70h] [rbp-11h]
  __int64 v28; // [rsp+78h] [rbp-9h]

  v8 = *(_QWORD *)this;
  if ( !v8 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v8, a2) )
    return 0;
  v12 = -1;
  if ( a3 )
  {
    v19 = (__int64 *)a3;
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    v20 = (unsigned int)(2 * v13 + 2);
  }
  else
  {
    v19 = &qword_1800439C0;
    v20 = 2;
  }
  v21 = a4;
  v22 = 16;
  if ( a5 )
  {
    v23 = (__int64 *)a5;
    do
      ++v12;
    while ( a5[v12] );
    v24 = (unsigned int)(2 * v12 + 2);
  }
  else
  {
    v23 = &qword_1800439C0;
    v24 = 2;
  }
  v26 = 4;
  v25 = &a6;
  v28 = 4;
  v27 = &a7;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a4);
  v14 = EtwEventWrite(*(_QWORD *)this, a2, 5, &v19);
  v18[0] = 0;
  v18[1] = 0;
  v15 = v14;
  EtwEventActivityIdControl(2, v18);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !v15 )
    return 0;
  EventManager::LogIt(v16, L"EventWrite error", v15);
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180005614  mov     [rsp-8+arg_10], rbx
0x180005619  push    rbp
0x18000561a  push    rsi
0x18000561b  push    rdi
0x18000561c  push    r14
0x18000561e  push    r15
0x180005620  lea     rbp, [rsp-0Fh]
0x180005625  sub     rsp, 90h
0x18000562c  mov     rax, cs:__security_cookie
0x180005633  xor     rax, rsp
0x180005636  mov     [rbp+2Fh+var_30], rax
0x18000563a  mov     r14, rcx
0x18000563d  xor     r15d, r15d
0x180005640  mov     rcx, [rcx]
0x180005643  mov     rdi, r9
0x180005646  mov     rbx, r8
0x180005649  mov     rsi, rdx
0x18000564c  test    rcx, rcx
0x18000564f  jz      loc_18000578A
0x180005655  call    cs:__imp_EtwEventEnabled
0x18000565c  nop     dword ptr [rax+rax+00h]
0x180005661  test    al, al
0x180005663  jz      loc_180005764
0x180005669  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000566d  lea     rdx, qword_1800439C0
0x180005674  test    rbx, rbx
0x180005677  jz      loc_1800057B3
0x18000567d  mov     [rbp+2Fh+var_80], rbx
0x180005681  mov     rax, rcx
0x180005684  inc     rax
0x180005687  cmp     [rbx+rax*2], r15w
0x18000568c  jnz     short loc_180005684
0x18000568e  lea     eax, ds:2[rax*2]
0x180005695  mov     dword ptr [rbp+2Fh+var_78+4], r15d
0x180005699  mov     dword ptr [rbp+2Fh+var_78], eax
0x18000569c  mov     rax, [rbp+2Fh+arg_20]
0x1800056a0  mov     [rbp+2Fh+var_70], rdi
0x1800056a4  mov     [rbp+2Fh+var_68], 10h
0x1800056ac  test    rax, rax
0x1800056af  jz      loc_1800057C4
0x1800056b5  mov     [rbp+2Fh+var_60], rax
0x1800056b9  inc     rcx
0x1800056bc  cmp     [rax+rcx*2], r15w
0x1800056c1  jnz     short loc_1800056B9
0x1800056c3  lea     eax, ds:2[rcx*2]
0x1800056ca  mov     dword ptr [rbp+2Fh+var_58+4], r15d
0x1800056ce  mov     dword ptr [rbp+2Fh+var_58], eax
0x1800056d1  lea     rax, [rbp+2Fh+arg_28]
0x1800056d5  mov     [rbp+2Fh+var_48], 4
0x1800056dd  mov     [rbp+2Fh+var_50], rax
0x1800056e1  lea     rcx, [r14+8]; lpCriticalSection
0x1800056e5  lea     rax, [rbp+2Fh+arg_30]
0x1800056e9  mov     [rbp+2Fh+var_38], 4
0x1800056f1  mov     [rbp+2Fh+var_40], rax
0x1800056f5  call    cs:__imp_EnterCriticalSection
0x1800056fc  nop     dword ptr [rax+rax+00h]
0x180005701  mov     rdx, rdi
0x180005704  mov     ecx, 2
0x180005709  call    cs:__imp_EtwEventActivityIdControl
0x180005710  nop     dword ptr [rax+rax+00h]
0x180005715  mov     rcx, [r14]
0x180005718  lea     r9, [rbp+2Fh+var_80]
0x18000571c  mov     r8d, 5
0x180005722  mov     rdx, rsi
0x180005725  call    cs:__imp_EtwEventWrite
0x18000572c  nop     dword ptr [rax+rax+00h]
0x180005731  lea     rdx, [rbp+2Fh+var_90]
0x180005735  mov     [rbp+2Fh+var_90], r15
0x180005739  mov     ecx, 2
0x18000573e  mov     [rbp+2Fh+var_88], r15
0x180005742  mov     edi, eax
0x180005744  call    cs:__imp_EtwEventActivityIdControl
0x18000574b  nop     dword ptr [rax+rax+00h]
0x180005750  lea     rcx, [r14+8]; lpCriticalSection
0x180005754  call    cs:__imp_LeaveCriticalSection
0x18000575b  nop     dword ptr [rax+rax+00h]
0x180005760  test    edi, edi
0x180005762  jnz     short loc_180005791
0x180005764  xor     eax, eax
0x180005766  mov     rcx, [rbp+2Fh+var_30]
0x18000576a  xor     rcx, rsp; StackCookie
0x18000576d  call    __security_check_cookie
0x180005772  mov     rbx, [rsp+0B0h+arg_10]
0x18000577a  add     rsp, 90h
0x180005781  pop     r15
0x180005783  pop     r14
0x180005785  pop     rdi
0x180005786  pop     rsi
0x180005787  pop     rbp
0x180005788  retn
0x18000578a  mov     eax, 1
0x18000578f  jmp     short loc_180005766
0x180005791  mov     r8d, edi; unsigned int
0x180005794  lea     rdx, aEventwriteErro; "EventWrite error"
0x18000579b  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800057a0  test    edi, edi
0x1800057a2  jg      short loc_1800057A8
0x1800057a4  mov     eax, edi
0x1800057a6  jmp     short loc_180005766
0x1800057a8  movzx   edi, di
0x1800057ab  or      edi, 80070000h
0x1800057b1  jmp     short loc_1800057A4
0x1800057b3  mov     [rbp+2Fh+var_80], rdx
0x1800057b7  mov     [rbp+2Fh+var_78], 2
0x1800057bf  jmp     loc_18000569C
0x1800057c4  mov     [rbp+2Fh+var_60], rdx
0x1800057c8  mov     [rbp+2Fh+var_58], 2
0x1800057d0  jmp     loc_1800056D1
```
