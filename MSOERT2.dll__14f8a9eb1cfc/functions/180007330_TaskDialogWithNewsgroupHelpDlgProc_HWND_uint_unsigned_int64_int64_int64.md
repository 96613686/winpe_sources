# TaskDialogWithNewsgroupHelpDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180007330`
- end: `0x1800073e3`
- name: `?TaskDialogWithNewsgroupHelpDlgProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `179`
- prototype: `int(HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180007330`
- `0x18000c910`
- `0x180014010`

## import_xrefs

- `USER32!GetParent` at `0x180007368`
- `USER32!GetParent` at `0x180007368`
- `SHELL32!ShellExecuteW` at `0x18000738f`
- `SHELL32!ShellExecuteW` at `0x18000738f`

## pseudocode

```c
__int64 __fastcall TaskDialogWithNewsgroupHelpDlgProc(HWND a1, int a2, __int64 a3, const WCHAR *a4, const WCHAR *a5)
{
  const WCHAR *v5; // rbx
  int v6; // edx
  HWND Parent; // rax
  __int64 v9; // rbx
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = a4;
  v6 = a2 - 2;
  if ( v6 )
  {
    if ( v6 != 1 )
      return 1;
    if ( a4 && *a4 || (v5 = a5) != 0 )
    {
      Parent = GetParent(a1);
      ShellExecuteW(Parent, L"open", v5, 0, 0, 1);
      v10[0] = 0;
      OEGetSqmSessionObj(v10);
      v9 = v10[0];
      if ( v10[0] )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)v10[0] + 24LL))(v10[0], 2416, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007330  push    rbx
0x180007332  sub     rsp, 40h
0x180007336  mov     rbx, r9
0x180007339  sub     edx, 2
0x18000733c  jz      loc_1800073DB
0x180007342  cmp     edx, 1
0x180007345  jz      short loc_180007351
0x180007347  mov     eax, 1
0x18000734c  jmp     loc_1800073DD
0x180007351  test    rbx, rbx
0x180007354  jz      short loc_18000735E
0x180007356  xor     eax, eax
0x180007358  cmp     ax, [r9]
0x18000735c  jnz     short loc_180007368
0x18000735e  mov     rbx, [rsp+48h+arg_20]
0x180007363  test    rbx, rbx
0x180007366  jz      short loc_1800073DB
0x180007368  call    cs:__imp_GetParent
0x18000736e  mov     [rsp+48h+nShowCmd], 1; nShowCmd
0x180007376  lea     rdx, Operation; "open"
0x18000737d  mov     rcx, rax; hwnd
0x180007380  mov     [rsp+48h+lpDirectory], 0; lpDirectory
0x180007389  xor     r9d, r9d; lpParameters
0x18000738c  mov     r8, rbx; lpFile
0x18000738f  call    cs:__imp_ShellExecuteW
0x180007395  lea     rcx, [rsp+48h+var_18]
0x18000739a  mov     [rsp+48h+var_18], 0
0x1800073a3  call    OEGetSqmSessionObj
0x1800073a8  mov     rbx, [rsp+48h+var_18]
0x1800073ad  test    rbx, rbx
0x1800073b0  jz      short loc_1800073DB
0x1800073b2  mov     rax, [rbx]
0x1800073b5  mov     edx, 970h
0x1800073ba  mov     r8d, 1
0x1800073c0  mov     rcx, rbx
0x1800073c3  mov     rax, [rax+18h]
0x1800073c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073cc  mov     rax, [rbx]
0x1800073cf  mov     rcx, rbx
0x1800073d2  mov     rax, [rax+10h]
0x1800073d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073db  xor     eax, eax
0x1800073dd  add     rsp, 40h
0x1800073e1  pop     rbx
0x1800073e2  retn
```
