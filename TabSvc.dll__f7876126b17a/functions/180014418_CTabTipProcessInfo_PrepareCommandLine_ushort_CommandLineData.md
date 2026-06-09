# CTabTipProcessInfo::_PrepareCommandLine(ushort * *,CommandLineData &)

- ea: `0x180014418`
- end: `0x1800144f4`
- name: `?_PrepareCommandLine@CTabTipProcessInfo@@IEBAHPEAPEAGAEAUCommandLineData@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(CTabTipProcessInfo *__hidden this, unsigned __int16 **, struct CommandLineData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002dd40`

## callees

- `0x1800037d0`
- `0x180014418`
- `0x18001bc04`
- `0x18001bffc`

## pseudocode

```c
__int64 __fastcall CTabTipProcessInfo::_PrepareCommandLine(
        CTabTipProcessInfo *this,
        unsigned __int16 **a2,
        struct CommandLineData *a3)
{
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  const wchar_t *v8; // r8
  const wchar_t *v9; // rcx
  const struct std::nothrow_t *v10; // rdx

  if ( !a2 )
    return 0;
  v5 = *((_DWORD *)a3 + 4) != 0 ? 113 : 100;
  if ( !*((_DWORD *)a3 + 5) )
    v5 = *((_DWORD *)a3 + 4) != 0 ? 100 : 87;
  v6 = 2 * v5;
  if ( !is_mul_ok(v5, 2u) )
    v6 = -1;
  v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  *a2 = v7;
  if ( !v7 )
    return 0;
  v8 = L"/SeekDesktop:";
  if ( !*((_DWORD *)a3 + 5) )
    v8 = &Data;
  v9 = L"/ManualLaunch";
  if ( !*((_DWORD *)a3 + 4) )
    v9 = &Data;
  if ( (unsigned int)StringCchPrintfW(
                       v7,
                       (unsigned int)v5,
                       L"/QuitInfo:%p;%p; %s %s",
                       *(_QWORD *)a3,
                       *((_QWORD *)a3 + 1),
                       v9,
                       v8) )
  {
    operator delete(*a2, v10);
    *a2 = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180014418  mov     [rsp+arg_0], rbx
0x18001441d  mov     [rsp+arg_8], rsi
0x180014422  push    rdi
0x180014423  sub     rsp, 40h
0x180014427  mov     rdi, r8
0x18001442a  mov     rbx, rdx
0x18001442d  test    rdx, rdx
0x180014430  jz      loc_1800144DB
0x180014436  mov     eax, [r8+10h]
0x18001443a  neg     eax
0x18001443c  mov     eax, 2
0x180014441  sbb     ecx, ecx
0x180014443  and     ecx, 0Dh
0x180014446  add     ecx, 57h ; 'W'
0x180014449  cmp     dword ptr [r8+14h], 0
0x18001444e  lea     esi, [rcx+0Dh]
0x180014451  cmovz   esi, ecx
0x180014454  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001445b  mul     rsi
0x18001445e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014465  cmovb   rax, rcx
0x180014469  mov     rcx, rax; unsigned __int64
0x18001446c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014471  mov     [rbx], rax
0x180014474  mov     r10, rax
0x180014477  test    rax, rax
0x18001447a  jz      short loc_1800144DB
0x18001447c  cmp     dword ptr [rdi+14h], 0
0x180014480  lea     rax, Data
0x180014487  mov     r9, [rdi]
0x18001448a  lea     r8, aSeekdesktop; "/SeekDesktop:"
0x180014491  cmovz   r8, rax
0x180014495  lea     rcx, aManuallaunch; "/ManualLaunch"
0x18001449c  cmp     dword ptr [rdi+10h], 0
0x1800144a0  mov     edx, esi; unsigned __int64
0x1800144a2  mov     [rsp+48h+var_18], r8
0x1800144a7  lea     r8, aQuitinfoPPSS; "/QuitInfo:%p;%p; %s %s"
0x1800144ae  cmovz   rcx, rax
0x1800144b2  mov     rax, [rdi+8]
0x1800144b6  mov     [rsp+48h+var_20], rcx
0x1800144bb  mov     rcx, r10; unsigned __int16 *
0x1800144be  mov     [rsp+48h+var_28], rax
0x1800144c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800144c8  test    eax, eax
0x1800144ca  jz      short loc_1800144ED
0x1800144cc  mov     rcx, [rbx]; void *
0x1800144cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800144d4  mov     qword ptr [rbx], 0
0x1800144db  xor     eax, eax
0x1800144dd  mov     rbx, [rsp+48h+arg_0]
0x1800144e2  mov     rsi, [rsp+48h+arg_8]
0x1800144e7  add     rsp, 40h
0x1800144eb  pop     rdi
0x1800144ec  retn
0x1800144ed  mov     eax, 1
0x1800144f2  jmp     short loc_1800144DD
```
