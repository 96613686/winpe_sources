# IsServiceIgnorable(ulong,ulong,ushort const *)

- ea: `0x1800231a4`
- end: `0x180023325`
- name: `?IsServiceIgnorable@@YA_NKKPEBG@Z`
- size: `385`
- prototype: `bool __fastcall(unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180023060`

## callees

- `0x180007660`
- `0x1800231a4`
- `0x1800239f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002323f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023275`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800232aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800232d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002323f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023275`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800232aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800232d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800232ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800232ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023301`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800231df`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800231df`

## string_xrefs

- `0x1800231ed`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x18002327f`: `\Microsoft\Windows\UpdateOrchestrator`
- `0x180023286`: `\Microsoft\Windows\WindowsUpdate\AUSessionConnect`
- `0x180023213`: `TermService`

## pseudocode

```c
char __fastcall IsServiceIgnorable(int a1, int a2, const unsigned __int16 *a3)
{
  unsigned int TagInformation; // eax
  const wchar_t *v6; // rdx
  _DWORD *i; // rbx
  __int64 v8; // r8
  const wchar_t *v9; // rdx
  const wchar_t **j; // rbx
  __int64 v11; // r8
  _QWORD v12[2]; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v13[3]; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v14[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h]
  HLOCAL hMem; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v14[0] = a1;
  v14[1] = a2;
  v15 = 0;
  hMem = 0;
  TagInformation = I_QueryTagInformation(0, 1, v14);
  if ( !TagInformation )
  {
    v13[1] = L"UsoSvc";
    v6 = L"TermService";
    v13[0] = L"TermService";
    v13[2] = L"DefragSvc";
    for ( i = v13; ; v6 = *(const wchar_t **)i )
    {
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      if ( !(unsigned int)_o__wcsnicmp(hMem, v6, v8) )
        goto LABEL_21;
      i += 2;
      if ( i == v14 )
        break;
    }
    if ( a3 )
    {
      if ( !(unsigned int)_o__wcsnicmp(hMem, L"Schedule", 8) )
      {
        v9 = L"\\Microsoft\\Windows\\UpdateOrchestrator";
        v12[0] = L"\\Microsoft\\Windows\\UpdateOrchestrator";
        v12[1] = L"\\Microsoft\\Windows\\WindowsUpdate\\AUSessionConnect";
        for ( j = (const wchar_t **)v12; ; v9 = *j )
        {
          v11 = -1;
          do
            ++v11;
          while ( v9[v11] );
          if ( !(unsigned int)_o__wcsnicmp(a3, v9, v11) )
            break;
          if ( ++j == v13 )
            goto LABEL_18;
        }
        goto LABEL_21;
      }
LABEL_18:
      if ( !(unsigned int)_o__wcsnicmp(L"\\Microsoft\\Windows\\rempl\\shell", a3, 30) )
      {
LABEL_21:
        if ( hMem )
          LocalFree(hMem);
        return 1;
      }
    }
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  wil::details::in1diag3::_Log_Win32(
    retaddr,
    (void *)0xB7,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
    (const char *)TagInformation,
    v12[0]);
  return 0;
}

```

## disassembly

```asm
0x1800231a4  mov     [rsp-18h+arg_18], rbx
0x1800231a9  push    rbp
0x1800231aa  push    rsi
0x1800231ab  push    rdi
0x1800231ac  mov     rbp, rsp
0x1800231af  sub     rsp, 70h
0x1800231b3  mov     rax, cs:__security_cookie
0x1800231ba  xor     rax, rsp
0x1800231bd  mov     [rbp+var_10], rax
0x1800231c1  xor     esi, esi
0x1800231c3  mov     [rbp+var_28], ecx
0x1800231c6  mov     rdi, r8
0x1800231c9  mov     [rbp+var_24], edx
0x1800231cc  xor     eax, eax
0x1800231ce  mov     [rbp+var_20], rsi
0x1800231d2  lea     r8, [rbp+var_28]
0x1800231d6  mov     [rbp+hMem], rax
0x1800231da  lea     edx, [rsi+1]
0x1800231dd  xor     ecx, ecx
0x1800231df  call    cs:__imp_I_QueryTagInformation
0x1800231e5  test    eax, eax
0x1800231e7  jz      short loc_180023208
0x1800231e9  mov     rcx, [rbp+18h]; this
0x1800231ed  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800231f4  mov     r9d, eax; char *
0x1800231f7  mov     edx, 0B7h; void *
0x1800231fc  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180023201  xor     al, al
0x180023203  jmp     loc_180023309
0x180023208  lea     rax, aUsosvc; "UsoSvc"
0x18002320f  mov     [rbp+var_38], rax
0x180023213  lea     rdx, aTermservice; "TermService"
0x18002321a  lea     rax, aDefragsvc; "DefragSvc"
0x180023221  mov     [rbp+var_40], rdx
0x180023225  mov     [rbp+var_30], rax
0x180023229  lea     rbx, [rbp+var_40]
0x18002322d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023231  inc     r8
0x180023234  cmp     [rdx+r8*2], si
0x180023239  jnz     short loc_180023231
0x18002323b  mov     rcx, [rbp+hMem]
0x18002323f  call    cs:__imp__o__wcsnicmp
0x180023245  test    eax, eax
0x180023247  jz      loc_1800232F8
0x18002324d  add     rbx, 8
0x180023251  lea     rax, [rbp+var_28]
0x180023255  cmp     rbx, rax
0x180023258  jz      short loc_18002325F
0x18002325a  mov     rdx, [rbx]
0x18002325d  jmp     short loc_18002322D
0x18002325f  test    rdi, rdi
0x180023262  jz      short loc_1800232E0
0x180023264  mov     rcx, [rbp+hMem]
0x180023268  lea     rdx, aSchedule; "Schedule"
0x18002326f  mov     r8d, 8
0x180023275  call    cs:__imp__o__wcsnicmp
0x18002327b  test    eax, eax
0x18002327d  jnz     short loc_1800232C6
0x18002327f  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\UpdateOrchestrato"...
0x180023286  lea     rax, aMicrosoftWindo; "\\Microsoft\\Windows\\WindowsUpdate\\AU"...
0x18002328d  mov     [rbp+var_50], rdx
0x180023291  mov     [rbp+var_48], rax
0x180023295  lea     rbx, [rbp+var_50]
0x180023299  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002329d  inc     r8
0x1800232a0  cmp     [rdx+r8*2], si
0x1800232a5  jnz     short loc_18002329D
0x1800232a7  mov     rcx, rdi
0x1800232aa  call    cs:__imp__o__wcsnicmp
0x1800232b0  test    eax, eax
0x1800232b2  jz      short loc_1800232F8
0x1800232b4  add     rbx, 8
0x1800232b8  lea     rax, [rbp+var_40]
0x1800232bc  cmp     rbx, rax
0x1800232bf  jz      short loc_1800232C6
0x1800232c1  mov     rdx, [rbx]
0x1800232c4  jmp     short loc_180023299
0x1800232c6  mov     r8d, 1Eh
0x1800232cc  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\rempl\\shell"
0x1800232d3  mov     rdx, rdi
0x1800232d6  call    cs:__imp__o__wcsnicmp
0x1800232dc  test    eax, eax
0x1800232de  jz      short loc_1800232F8
0x1800232e0  mov     rcx, [rbp+hMem]; hMem
0x1800232e4  test    rcx, rcx
0x1800232e7  jz      loc_180023201
0x1800232ed  call    cs:__imp_LocalFree
0x1800232f3  jmp     loc_180023201
0x1800232f8  mov     rcx, [rbp+hMem]; hMem
0x1800232fc  test    rcx, rcx
0x1800232ff  jz      short loc_180023307
0x180023301  call    cs:__imp_LocalFree
0x180023307  mov     al, 1
0x180023309  mov     rcx, [rbp+var_10]
0x18002330d  xor     rcx, rsp; StackCookie
0x180023310  call    __security_check_cookie
0x180023315  mov     rbx, [rsp+70h+arg_18]
0x18002331d  add     rsp, 70h
0x180023321  pop     rdi
0x180023322  pop     rsi
0x180023323  pop     rbp
0x180023324  retn
```
