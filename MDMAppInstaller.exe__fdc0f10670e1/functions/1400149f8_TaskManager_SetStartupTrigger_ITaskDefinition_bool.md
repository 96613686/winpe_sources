# TaskManager::SetStartupTrigger(ITaskDefinition *,bool)

- ea: `0x1400149f8`
- end: `0x140014bdb`
- name: `?SetStartupTrigger@TaskManager@@CAJPEAUITaskDefinition@@_N@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct ITaskDefinition *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140013c90`

## callees

- `0x14000740c`
- `0x1400149f8`
- `0x14001a8d0`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140014aed`
- `OLEAUT32!__imp_SysAllocString` at `0x140014b22`
- `OLEAUT32!__imp_SysAllocString` at `0x140014aed`
- `OLEAUT32!__imp_SysAllocString` at `0x140014b22`
- `OLEAUT32!__imp_SysFreeString` at `0x140014b4c`
- `OLEAUT32!__imp_SysFreeString` at `0x140014b55`
- `OLEAUT32!__imp_SysFreeString` at `0x140014b4c`
- `OLEAUT32!__imp_SysFreeString` at `0x140014b55`

## pseudocode

```c
__int64 __fastcall TaskManager::SetStartupTrigger(struct ITaskDefinition *a1)
{
  OLECHAR *v1; // rdi
  OLECHAR *v2; // rsi
  int v3; // ebx
  BSTR v4; // rax
  BSTR v5; // rax
  __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+28h] [rbp-30h] BYREF
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  OLECHAR psz[4]; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h]

  v1 = 0;
  v2 = 0;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  *(_QWORD *)psz = *(_QWORD *)L"PT15S";
  v11 = *(_DWORD *)L"S";
  if ( !a1 )
  {
    v3 = -2147024809;
    goto LABEL_15;
  }
  v3 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))a1->lpVtbl->get_Triggers)(a1, &v8);
  if ( v3 >= 0 )
  {
    if ( !v8 )
    {
LABEL_5:
      v3 = -2147024882;
      goto LABEL_15;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v8 + 80LL))(v8, 8, &v9);
    if ( v3 >= 0 )
    {
      if ( !v9 )
        goto LABEL_5;
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
             v9,
             &GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb,
             &v7);
      if ( v3 >= 0 )
      {
        if ( !v7 )
          goto LABEL_5;
        v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 152LL))(v7, 0xFFFFFFFFLL);
        if ( v3 >= 0 )
        {
          v4 = SysAllocString(psz);
          v1 = v4;
          if ( !v4 )
            goto LABEL_5;
          v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v7 + 168LL))(v7, v4);
          if ( v3 >= 0 )
          {
            v5 = SysAllocString(L"Resume On System Startup");
            v2 = v5;
            if ( !v5 )
              goto LABEL_5;
            v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v7 + 72LL))(v7, v5);
          }
        }
      }
    }
  }
LABEL_15:
  SysFreeString(v1);
  SysFreeString(v2);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = 0;
  }
  if ( v3 < 0 )
    LogError(L"SetStartupTrigger() failed.  Error = 0x%1!x!.", (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400149f8  push    rbp
0x1400149fa  push    rbx
0x1400149fb  push    rsi
0x1400149fc  push    rdi
0x1400149fd  mov     rbp, rsp
0x140014a00  sub     rsp, 58h
0x140014a04  mov     rax, cs:__security_cookie
0x140014a0b  xor     rax, rsp
0x140014a0e  mov     [rbp+var_10], rax
0x140014a12  movsd   xmm0, qword ptr cs:aPt15s; "PT15S"
0x140014a1a  xor     edi, edi
0x140014a1c  mov     eax, dword ptr cs:aPt15s+8; "S"
0x140014a22  xor     esi, esi
0x140014a24  mov     [rbp+var_28], 0
0x140014a2c  mov     [rbp+var_38], 0
0x140014a34  mov     [rbp+var_30], 0
0x140014a3c  movsd   qword ptr [rbp+psz], xmm0
0x140014a41  mov     [rbp+var_18], eax
0x140014a44  test    rcx, rcx
0x140014a47  jnz     short loc_140014A53
0x140014a49  mov     ebx, 80070057h
0x140014a4e  jmp     loc_140014B49
0x140014a53  mov     rax, [rcx]
0x140014a56  lea     rdx, [rbp+var_30]
0x140014a5a  mov     rax, [rax+48h]
0x140014a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a63  mov     ebx, eax
0x140014a65  test    eax, eax
0x140014a67  js      loc_140014B49
0x140014a6d  mov     rcx, [rbp+var_30]
0x140014a71  test    rcx, rcx
0x140014a74  jnz     short loc_140014A80
0x140014a76  mov     ebx, 8007000Eh
0x140014a7b  jmp     loc_140014B49
0x140014a80  mov     rax, [rcx]
0x140014a83  lea     r8, [rbp+var_28]
0x140014a87  mov     edx, 8
0x140014a8c  mov     rax, [rax+50h]
0x140014a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a95  mov     ebx, eax
0x140014a97  test    eax, eax
0x140014a99  js      loc_140014B49
0x140014a9f  mov     rcx, [rbp+var_28]
0x140014aa3  test    rcx, rcx
0x140014aa6  jz      short loc_140014A76
0x140014aa8  mov     rax, [rcx]
0x140014aab  lea     r8, [rbp+var_38]
0x140014aaf  lea     rdx, _GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb
0x140014ab6  mov     rax, [rax]
0x140014ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014abe  mov     ebx, eax
0x140014ac0  test    eax, eax
0x140014ac2  js      loc_140014B49
0x140014ac8  mov     rcx, [rbp+var_38]
0x140014acc  test    rcx, rcx
0x140014acf  jz      short loc_140014A76
0x140014ad1  mov     rax, [rcx]
0x140014ad4  or      edx, 0FFFFFFFFh
0x140014ad7  mov     rax, [rax+98h]
0x140014ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ae3  mov     ebx, eax
0x140014ae5  test    eax, eax
0x140014ae7  js      short loc_140014B49
0x140014ae9  lea     rcx, [rbp+psz]; psz
0x140014aed  call    cs:__imp_SysAllocString
0x140014af3  mov     rdi, rax
0x140014af6  test    rax, rax
0x140014af9  jz      loc_140014A76
0x140014aff  mov     rcx, [rbp+var_38]
0x140014b03  mov     rdx, rdi
0x140014b06  mov     rax, [rcx]
0x140014b09  mov     rax, [rax+0A8h]
0x140014b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b15  mov     ebx, eax
0x140014b17  test    eax, eax
0x140014b19  js      short loc_140014B49
0x140014b1b  lea     rcx, aResumeOnSystem; "Resume On System Startup"
0x140014b22  call    cs:__imp_SysAllocString
0x140014b28  mov     rsi, rax
0x140014b2b  test    rax, rax
0x140014b2e  jz      loc_140014A76
0x140014b34  mov     rcx, [rbp+var_38]
0x140014b38  mov     rdx, rsi
0x140014b3b  mov     rax, [rcx]
0x140014b3e  mov     rax, [rax+48h]
0x140014b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b47  mov     ebx, eax
0x140014b49  mov     rcx, rdi; bstrString
0x140014b4c  call    cs:__imp_SysFreeString
0x140014b52  mov     rcx, rsi; bstrString
0x140014b55  call    cs:__imp_SysFreeString
0x140014b5b  mov     rcx, [rbp+var_30]
0x140014b5f  test    rcx, rcx
0x140014b62  jz      short loc_140014B78
0x140014b64  mov     rax, [rcx]
0x140014b67  mov     rax, [rax+10h]
0x140014b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b70  mov     [rbp+var_30], 0
0x140014b78  mov     rcx, [rbp+var_28]
0x140014b7c  test    rcx, rcx
0x140014b7f  jz      short loc_140014B95
0x140014b81  mov     rax, [rcx]
0x140014b84  mov     rax, [rax+10h]
0x140014b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b8d  mov     [rbp+var_28], 0
0x140014b95  mov     rcx, [rbp+var_38]
0x140014b99  test    rcx, rcx
0x140014b9c  jz      short loc_140014BB2
0x140014b9e  mov     rax, [rcx]
0x140014ba1  mov     rax, [rax+10h]
0x140014ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014baa  mov     [rbp+var_38], 0
0x140014bb2  test    ebx, ebx
0x140014bb4  jns     short loc_140014BC4
0x140014bb6  mov     edx, ebx
0x140014bb8  lea     rcx, aSetstartuptrig; "SetStartupTrigger() failed.  Error = 0x"...
0x140014bbf  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014bc4  mov     eax, ebx
0x140014bc6  mov     rcx, [rbp+var_10]
0x140014bca  xor     rcx, rsp; StackCookie
0x140014bcd  call    __security_check_cookie
0x140014bd2  add     rsp, 58h
0x140014bd6  pop     rdi
0x140014bd7  pop     rsi
0x140014bd8  pop     rbx
0x140014bd9  pop     rbp
0x140014bda  retn
```
