# TaskManager::SetTaskPrincipalToSystem(ITaskDefinition *)

- ea: `0x140014e1c`
- end: `0x140014f25`
- name: `?SetTaskPrincipalToSystem@TaskManager@@CAJPEAUITaskDefinition@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct ITaskDefinition *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140013c90`

## callees

- `0x14000740c`
- `0x140014e1c`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140014e76`
- `OLEAUT32!__imp_SysAllocString` at `0x140014eac`
- `OLEAUT32!__imp_SysAllocString` at `0x140014e76`
- `OLEAUT32!__imp_SysAllocString` at `0x140014eac`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ef2`
- `OLEAUT32!__imp_SysFreeString` at `0x140014efb`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ef2`
- `OLEAUT32!__imp_SysFreeString` at `0x140014efb`

## string_xrefs

- `0x140014f07`: `SetTaskPrincipalToSystem() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall TaskManager::SetTaskPrincipalToSystem(struct ITaskDefinition *a1)
{
  OLECHAR *v1; // rdi
  OLECHAR *v2; // rsi
  int v3; // ebx
  BSTR v4; // rax
  BSTR v5; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v7 = 0;
  v2 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    goto LABEL_13;
  }
  v3 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))a1->lpVtbl->get_Principal)(a1, &v7);
  if ( v3 < 0 )
    goto LABEL_11;
  if ( !v7 )
  {
    v3 = -2147024882;
    goto LABEL_13;
  }
  v4 = SysAllocString(L"LocalSystem");
  v1 = v4;
  if ( !v4 )
    goto LABEL_7;
  v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v7 + 64LL))(v7, v4);
  if ( v3 >= 0 )
  {
    v5 = SysAllocString(L"S-1-5-18");
    v2 = v5;
    if ( !v5 )
    {
LABEL_7:
      v3 = -2147024882;
      goto LABEL_11;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v7 + 96LL))(v7, v5);
  }
LABEL_11:
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = 0;
  }
LABEL_13:
  SysFreeString(v1);
  SysFreeString(v2);
  if ( v3 < 0 )
    LogError(L"SetTaskPrincipalToSystem() failed.  Error = 0x%1!x!.", (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140014e1c  mov     [rsp+arg_8], rbx
0x140014e21  mov     [rsp+arg_10], rsi
0x140014e26  push    rdi
0x140014e27  sub     rsp, 20h
0x140014e2b  xor     edi, edi
0x140014e2d  mov     [rsp+28h+arg_0], 0
0x140014e36  xor     esi, esi
0x140014e38  test    rcx, rcx
0x140014e3b  jnz     short loc_140014E47
0x140014e3d  mov     ebx, 80070057h
0x140014e42  jmp     loc_140014EEF
0x140014e47  mov     rax, [rcx]
0x140014e4a  lea     rdx, [rsp+28h+arg_0]
0x140014e4f  mov     rax, [rax+78h]
0x140014e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e58  mov     ebx, eax
0x140014e5a  test    eax, eax
0x140014e5c  js      short loc_140014ED0
0x140014e5e  cmp     [rsp+28h+arg_0], rsi
0x140014e63  jnz     short loc_140014E6F
0x140014e65  mov     ebx, 8007000Eh
0x140014e6a  jmp     loc_140014EEF
0x140014e6f  lea     rcx, aLocalsystem; "LocalSystem"
0x140014e76  call    cs:__imp_SysAllocString
0x140014e7c  mov     rdi, rax
0x140014e7f  test    rax, rax
0x140014e82  jnz     short loc_140014E8B
0x140014e84  mov     ebx, 8007000Eh
0x140014e89  jmp     short loc_140014ED0
0x140014e8b  mov     rcx, [rsp+28h+arg_0]
0x140014e90  mov     rdx, rdi
0x140014e93  mov     rax, [rcx]
0x140014e96  mov     rax, [rax+40h]
0x140014e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e9f  mov     ebx, eax
0x140014ea1  test    eax, eax
0x140014ea3  js      short loc_140014ED0
0x140014ea5  lea     rcx, aS1518_0; "S-1-5-18"
0x140014eac  call    cs:__imp_SysAllocString
0x140014eb2  mov     rsi, rax
0x140014eb5  test    rax, rax
0x140014eb8  jz      short loc_140014E84
0x140014eba  mov     rcx, [rsp+28h+arg_0]
0x140014ebf  mov     rdx, rsi
0x140014ec2  mov     rax, [rcx]
0x140014ec5  mov     rax, [rax+60h]
0x140014ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ece  mov     ebx, eax
0x140014ed0  mov     rcx, [rsp+28h+arg_0]
0x140014ed5  test    rcx, rcx
0x140014ed8  jz      short loc_140014EEF
0x140014eda  mov     rax, [rcx]
0x140014edd  mov     rax, [rax+10h]
0x140014ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ee6  mov     [rsp+28h+arg_0], 0
0x140014eef  mov     rcx, rdi; bstrString
0x140014ef2  call    cs:__imp_SysFreeString
0x140014ef8  mov     rcx, rsi; bstrString
0x140014efb  call    cs:__imp_SysFreeString
0x140014f01  test    ebx, ebx
0x140014f03  jns     short loc_140014F13
0x140014f05  mov     edx, ebx
0x140014f07  lea     rcx, aSettaskprincip; "SetTaskPrincipalToSystem() failed.  Err"...
0x140014f0e  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014f13  mov     rsi, [rsp+28h+arg_10]
0x140014f18  mov     eax, ebx
0x140014f1a  mov     rbx, [rsp+28h+arg_8]
0x140014f1f  add     rsp, 20h
0x140014f23  pop     rdi
0x140014f24  retn
```
