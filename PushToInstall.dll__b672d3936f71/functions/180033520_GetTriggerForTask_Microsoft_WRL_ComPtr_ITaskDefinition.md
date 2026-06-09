# GetTriggerForTask(Microsoft::WRL::ComPtr<ITaskDefinition> &)

- ea: `0x180033520`
- end: `0x180033649`
- name: `?GetTriggerForTask@@YA?AV?$ComPtr@UITrigger@@@WRL@Microsoft@@AEAV?$ComPtr@UITaskDefinition@@@23@@Z`
- size: `297`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800338b4`
- `0x180033af0`

## callees

- `0x18002008c`
- `0x180033520`
- `0x18004f010`

## string_xrefs

- `0x1800335f5`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x18003360a`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x18003361f`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033637`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`

## pseudocode

```c
_QWORD *__fastcall GetTriggerForTask(_QWORD *a1, _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  int v9; // [rsp+48h] [rbp+18h] BYREF
  __int64 v10; // [rsp+50h] [rbp+20h] BYREF

  v10 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 72LL))(*a2, &v10);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v3,
      0);
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, &v9);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v4,
      0);
  if ( v9 < 1 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)0x8007000DLL,
      0);
  *a1 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v10 + 64LL))(v10, 1, a1);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v5,
      1);
  v6 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180033520  mov     [rsp-8+arg_18], rbx
0x180033525  mov     [rsp-8+arg_0], rcx
0x18003352a  push    rbp
0x18003352b  mov     rbp, rsp
0x18003352e  sub     rsp, 30h
0x180033532  mov     rbx, rcx
0x180033535  mov     [rbp+var_10], 0
0x18003353c  mov     [rbp+arg_10], 0
0x180033544  mov     rcx, [rdx]
0x180033547  mov     rax, [rcx]
0x18003354a  lea     rdx, [rbp+arg_10]
0x18003354e  mov     rax, [rax+48h]
0x180033552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033557  mov     rcx, [rbp+8]; this
0x18003355b  test    eax, eax
0x18003355d  js      loc_180033607
0x180033563  mov     [rbp+arg_8], 0
0x18003356a  mov     rcx, [rbp+arg_10]
0x18003356e  mov     rax, [rcx]
0x180033571  lea     rdx, [rbp+arg_8]
0x180033575  mov     rax, [rax+38h]
0x180033579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003357e  mov     rcx, [rbp+8]; this
0x180033582  test    eax, eax
0x180033584  js      loc_18003361C
0x18003358a  mov     edx, 1
0x18003358f  cmp     [rbp+arg_8], edx
0x180033592  setl    al
0x180033595  mov     rcx, [rbp+8]; this
0x180033599  test    al, al
0x18003359b  jnz     loc_180033631
0x1800335a1  mov     qword ptr [rbx], 0
0x1800335a8  mov     [rbp+var_10], edx
0x1800335ab  mov     rcx, [rbp+arg_10]
0x1800335af  mov     rax, [rcx]
0x1800335b2  mov     r8, rbx
0x1800335b5  mov     rax, [rax+40h]
0x1800335b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335be  mov     rcx, [rbp+8]; this
0x1800335c2  test    eax, eax
0x1800335c4  js      short loc_1800335F2
0x1800335c6  mov     rcx, [rbp+arg_10]
0x1800335ca  test    rcx, rcx
0x1800335cd  jz      short loc_1800335E4
0x1800335cf  mov     [rbp+arg_10], 0
0x1800335d7  mov     rax, [rcx]
0x1800335da  mov     rax, [rax+10h]
0x1800335de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335e3  nop
0x1800335e4  mov     rax, rbx
0x1800335e7  mov     rbx, [rsp+30h+arg_18]
0x1800335ec  add     rsp, 30h
0x1800335f0  pop     rbp
0x1800335f1  retn
0x1800335f2  mov     r9d, eax; char *
0x1800335f5  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800335fc  mov     edx, 42h ; 'B'; void *
0x180033601  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033607  mov     r9d, eax; char *
0x18003360a  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033611  mov     edx, 3Bh ; ';'; void *
0x180033616  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003361c  mov     r9d, eax; char *
0x18003361f  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033626  mov     edx, 3Eh ; '>'; void *
0x18003362b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033631  mov     r9d, 8007000Dh; char *
0x180033637  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003363e  mov     edx, 3Fh ; '?'; void *
0x180033643  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
