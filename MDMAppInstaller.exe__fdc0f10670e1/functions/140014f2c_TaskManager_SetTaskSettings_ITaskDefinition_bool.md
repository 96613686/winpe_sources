# TaskManager::SetTaskSettings(ITaskDefinition *,bool)

- ea: `0x140014f2c`
- end: `0x140015052`
- name: `?SetTaskSettings@TaskManager@@CAJPEAUITaskDefinition@@_N@Z`
- size: `294`
- prototype: `__int64 __fastcall(struct ITaskDefinition *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x140013c90`

## callees

- `0x14000740c`
- `0x140014f2c`
- `0x14001a8d0`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140014fda`
- `OLEAUT32!__imp_SysAllocString` at `0x140014fda`
- `OLEAUT32!__imp_SysFreeString` at `0x140015001`
- `OLEAUT32!__imp_SysFreeString` at `0x140015001`

## string_xrefs

- `0x14001502c`: `SetTaskSettings() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall TaskManager::SetTaskSettings(struct ITaskDefinition *a1)
{
  OLECHAR *v1; // rdi
  int v2; // ebx
  BSTR v3; // rax
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  OLECHAR psz[4]; // [rsp+28h] [rbp-20h] BYREF
  wchar_t v7; // [rsp+30h] [rbp-18h]

  v1 = 0;
  v5 = 0;
  *(_QWORD *)psz = *(_QWORD *)L"PT5M";
  v7 = aPt5m[4];
  if ( !a1 )
  {
    v2 = -2147024809;
    goto LABEL_10;
  }
  v2 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))a1->lpVtbl->get_Settings)(a1, &v5);
  if ( v2 >= 0 )
  {
    if ( !v5 )
    {
LABEL_5:
      v2 = -2147024882;
      goto LABEL_10;
    }
    v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 240LL))(v5, 0xFFFFFFFFLL);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 96LL))(v5, 3);
      if ( v2 >= 0 )
      {
        v3 = SysAllocString(psz);
        v1 = v3;
        if ( !v3 )
          goto LABEL_5;
        v2 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v5 + 80LL))(v5, v3);
      }
    }
  }
LABEL_10:
  SysFreeString(v1);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v5 = 0;
  }
  if ( v2 < 0 )
    LogError(L"SetTaskSettings() failed.  Error = 0x%1!x!.", (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140014f2c  mov     [rsp+arg_8], rbx
0x140014f31  push    rdi
0x140014f32  sub     rsp, 40h
0x140014f36  mov     rax, cs:__security_cookie
0x140014f3d  xor     rax, rsp
0x140014f40  mov     [rsp+48h+var_10], rax
0x140014f45  movsd   xmm0, qword ptr cs:aPt5m; "PT5M"
0x140014f4d  xor     edi, edi
0x140014f4f  movzx   eax, word ptr cs:aPt5m+8; ""
0x140014f56  mov     [rsp+48h+var_28], 0
0x140014f5f  movsd   qword ptr [rsp+48h+psz], xmm0
0x140014f65  mov     [rsp+48h+var_18], ax
0x140014f6a  test    rcx, rcx
0x140014f6d  jnz     short loc_140014F79
0x140014f6f  mov     ebx, 80070057h
0x140014f74  jmp     loc_140014FFE
0x140014f79  mov     rax, [rcx]
0x140014f7c  lea     rdx, [rsp+48h+var_28]
0x140014f81  mov     rax, [rax+58h]
0x140014f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f8a  mov     ebx, eax
0x140014f8c  test    eax, eax
0x140014f8e  js      short loc_140014FFE
0x140014f90  mov     rcx, [rsp+48h+var_28]
0x140014f95  test    rcx, rcx
0x140014f98  jnz     short loc_140014FA1
0x140014f9a  mov     ebx, 8007000Eh
0x140014f9f  jmp     short loc_140014FFE
0x140014fa1  mov     rax, [rcx]
0x140014fa4  or      edx, 0FFFFFFFFh
0x140014fa7  mov     rax, [rax+0F0h]
0x140014fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014fb3  mov     ebx, eax
0x140014fb5  test    eax, eax
0x140014fb7  js      short loc_140014FFE
0x140014fb9  mov     rcx, [rsp+48h+var_28]
0x140014fbe  mov     edx, 3
0x140014fc3  mov     rax, [rcx]
0x140014fc6  mov     rax, [rax+60h]
0x140014fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014fcf  mov     ebx, eax
0x140014fd1  test    eax, eax
0x140014fd3  js      short loc_140014FFE
0x140014fd5  lea     rcx, [rsp+48h+psz]; psz
0x140014fda  call    cs:__imp_SysAllocString
0x140014fe0  mov     rdi, rax
0x140014fe3  test    rax, rax
0x140014fe6  jz      short loc_140014F9A
0x140014fe8  mov     rcx, [rsp+48h+var_28]
0x140014fed  mov     rdx, rdi
0x140014ff0  mov     rax, [rcx]
0x140014ff3  mov     rax, [rax+50h]
0x140014ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ffc  mov     ebx, eax
0x140014ffe  mov     rcx, rdi; bstrString
0x140015001  call    cs:__imp_SysFreeString
0x140015007  mov     rcx, [rsp+48h+var_28]
0x14001500c  test    rcx, rcx
0x14001500f  jz      short loc_140015026
0x140015011  mov     rax, [rcx]
0x140015014  mov     rax, [rax+10h]
0x140015018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001501d  mov     [rsp+48h+var_28], 0
0x140015026  test    ebx, ebx
0x140015028  jns     short loc_140015038
0x14001502a  mov     edx, ebx
0x14001502c  lea     rcx, aSettasksetting; "SetTaskSettings() failed.  Error = 0x%1"...
0x140015033  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140015038  mov     eax, ebx
0x14001503a  mov     rcx, [rsp+48h+var_10]
0x14001503f  xor     rcx, rsp; StackCookie
0x140015042  call    __security_check_cookie
0x140015047  mov     rbx, [rsp+48h+arg_8]
0x14001504c  add     rsp, 40h
0x140015050  pop     rdi
0x140015051  retn
```
