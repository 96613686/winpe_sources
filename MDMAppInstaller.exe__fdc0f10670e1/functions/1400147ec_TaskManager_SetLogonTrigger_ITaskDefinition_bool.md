# TaskManager::SetLogonTrigger(ITaskDefinition *,bool)

- ea: `0x1400147ec`
- end: `0x1400149f1`
- name: `?SetLogonTrigger@TaskManager@@CAJPEAUITaskDefinition@@_N@Z`
- size: `517`
- prototype: `__int64 __fastcall(struct ITaskDefinition *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140013c90`

## callees

- `0x14000740c`
- `0x1400147ec`
- `0x14001a8d0`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400148f7`
- `OLEAUT32!__imp_SysAllocString` at `0x14001492c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400148f7`
- `OLEAUT32!__imp_SysAllocString` at `0x14001492c`
- `OLEAUT32!__imp_SysFreeString` at `0x140014956`
- `OLEAUT32!__imp_SysFreeString` at `0x14001495f`
- `OLEAUT32!__imp_SysFreeString` at `0x140014956`
- `OLEAUT32!__imp_SysFreeString` at `0x14001495f`

## pseudocode

```c
__int64 __fastcall TaskManager::SetLogonTrigger(struct ITaskDefinition *a1, unsigned __int8 a2)
{
  OLECHAR *v2; // rdi
  OLECHAR *v3; // rsi
  int v5; // ebx
  BSTR v6; // rax
  BSTR v7; // rax
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+28h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  OLECHAR psz[4]; // [rsp+38h] [rbp-18h] BYREF
  wchar_t v13; // [rsp+40h] [rbp-10h]

  v2 = 0;
  v3 = 0;
  v11 = 0;
  v9 = 0;
  v10 = 0;
  *(_QWORD *)psz = *(_QWORD *)L"PT5S";
  v13 = aPt5s[4];
  if ( !a1 )
  {
    v5 = -2147024809;
    goto LABEL_15;
  }
  v5 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))a1->lpVtbl->get_Triggers)(a1, &v10);
  if ( v5 >= 0 )
  {
    if ( !v10 )
    {
LABEL_5:
      v5 = -2147024882;
      goto LABEL_15;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 80LL))(v10, 9, &v11);
    if ( v5 >= 0 )
    {
      if ( !v11 )
        goto LABEL_5;
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v11)(
             v11,
             &GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c,
             &v9);
      if ( v5 >= 0 )
      {
        if ( !v9 )
          goto LABEL_5;
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 152LL))(v9, (unsigned __int16)((a2 ^ 1) - 1));
        if ( v5 >= 0 )
        {
          v6 = SysAllocString(psz);
          v2 = v6;
          if ( !v6 )
            goto LABEL_5;
          v5 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v9 + 168LL))(v9, v6);
          if ( v5 >= 0 )
          {
            v7 = SysAllocString(L"Resume On User Logon");
            v3 = v7;
            if ( !v7 )
              goto LABEL_5;
            v5 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v9 + 72LL))(v9, v7);
          }
        }
      }
    }
  }
LABEL_15:
  SysFreeString(v2);
  SysFreeString(v3);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v5 < 0 )
    LogError(L"SetLogonTrigger() failed.  Error = 0x%1!x!.", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400147ec  mov     [rsp-18h+arg_8], rbx
0x1400147f1  mov     [rsp-18h+arg_10], rsi
0x1400147f6  push    rbp
0x1400147f7  push    rdi
0x1400147f8  push    r14
0x1400147fa  mov     rbp, rsp
0x1400147fd  sub     rsp, 50h
0x140014801  mov     rax, cs:__security_cookie
0x140014808  xor     rax, rsp
0x14001480b  mov     [rbp+var_8], rax
0x14001480f  movsd   xmm0, qword ptr cs:aPt5s; "PT5S"
0x140014817  xor     edi, edi
0x140014819  movzx   eax, word ptr cs:aPt5s+8; ""
0x140014820  xor     esi, esi
0x140014822  mov     [rbp+var_20], 0
0x14001482a  mov     r14b, dl
0x14001482d  mov     [rbp+var_30], 0
0x140014835  mov     [rbp+var_28], 0
0x14001483d  movsd   qword ptr [rbp+psz], xmm0
0x140014842  mov     [rbp+var_10], ax
0x140014846  test    rcx, rcx
0x140014849  jnz     short loc_140014855
0x14001484b  mov     ebx, 80070057h
0x140014850  jmp     loc_140014953
0x140014855  mov     rax, [rcx]
0x140014858  lea     rdx, [rbp+var_28]
0x14001485c  mov     rax, [rax+48h]
0x140014860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014865  mov     ebx, eax
0x140014867  test    eax, eax
0x140014869  js      loc_140014953
0x14001486f  mov     rcx, [rbp+var_28]
0x140014873  test    rcx, rcx
0x140014876  jnz     short loc_140014882
0x140014878  mov     ebx, 8007000Eh
0x14001487d  jmp     loc_140014953
0x140014882  mov     rax, [rcx]
0x140014885  lea     r8, [rbp+var_20]
0x140014889  mov     edx, 9
0x14001488e  mov     rax, [rax+50h]
0x140014892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014897  mov     ebx, eax
0x140014899  test    eax, eax
0x14001489b  js      loc_140014953
0x1400148a1  mov     rcx, [rbp+var_20]
0x1400148a5  test    rcx, rcx
0x1400148a8  jz      short loc_140014878
0x1400148aa  mov     rax, [rcx]
0x1400148ad  lea     r8, [rbp+var_30]
0x1400148b1  lea     rdx, _GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c
0x1400148b8  mov     rax, [rax]
0x1400148bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400148c0  mov     ebx, eax
0x1400148c2  test    eax, eax
0x1400148c4  js      loc_140014953
0x1400148ca  mov     rcx, [rbp+var_30]
0x1400148ce  test    rcx, rcx
0x1400148d1  jz      short loc_140014878
0x1400148d3  mov     rax, [rcx]
0x1400148d6  xor     r14b, 1
0x1400148da  movzx   edx, r14b
0x1400148de  dec     dx
0x1400148e1  mov     rax, [rax+98h]
0x1400148e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400148ed  mov     ebx, eax
0x1400148ef  test    eax, eax
0x1400148f1  js      short loc_140014953
0x1400148f3  lea     rcx, [rbp+psz]; psz
0x1400148f7  call    cs:__imp_SysAllocString
0x1400148fd  mov     rdi, rax
0x140014900  test    rax, rax
0x140014903  jz      loc_140014878
0x140014909  mov     rcx, [rbp+var_30]
0x14001490d  mov     rdx, rdi
0x140014910  mov     rax, [rcx]
0x140014913  mov     rax, [rax+0A8h]
0x14001491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001491f  mov     ebx, eax
0x140014921  test    eax, eax
0x140014923  js      short loc_140014953
0x140014925  lea     rcx, aResumeOnUserLo; "Resume On User Logon"
0x14001492c  call    cs:__imp_SysAllocString
0x140014932  mov     rsi, rax
0x140014935  test    rax, rax
0x140014938  jz      loc_140014878
0x14001493e  mov     rcx, [rbp+var_30]
0x140014942  mov     rdx, rsi
0x140014945  mov     rax, [rcx]
0x140014948  mov     rax, [rax+48h]
0x14001494c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014951  mov     ebx, eax
0x140014953  mov     rcx, rdi; bstrString
0x140014956  call    cs:__imp_SysFreeString
0x14001495c  mov     rcx, rsi; bstrString
0x14001495f  call    cs:__imp_SysFreeString
0x140014965  mov     rcx, [rbp+var_28]
0x140014969  test    rcx, rcx
0x14001496c  jz      short loc_140014982
0x14001496e  mov     rax, [rcx]
0x140014971  mov     rax, [rax+10h]
0x140014975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001497a  mov     [rbp+var_28], 0
0x140014982  mov     rcx, [rbp+var_20]
0x140014986  test    rcx, rcx
0x140014989  jz      short loc_14001499F
0x14001498b  mov     rax, [rcx]
0x14001498e  mov     rax, [rax+10h]
0x140014992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014997  mov     [rbp+var_20], 0
0x14001499f  mov     rcx, [rbp+var_30]
0x1400149a3  test    rcx, rcx
0x1400149a6  jz      short loc_1400149BC
0x1400149a8  mov     rax, [rcx]
0x1400149ab  mov     rax, [rax+10h]
0x1400149af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400149b4  mov     [rbp+var_30], 0
0x1400149bc  test    ebx, ebx
0x1400149be  jns     short loc_1400149CE
0x1400149c0  mov     edx, ebx
0x1400149c2  lea     rcx, aSetlogontrigge; "SetLogonTrigger() failed.  Error = 0x%1"...
0x1400149c9  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400149ce  mov     eax, ebx
0x1400149d0  mov     rcx, [rbp+var_8]
0x1400149d4  xor     rcx, rsp; StackCookie
0x1400149d7  call    __security_check_cookie
0x1400149dc  lea     r11, [rsp+50h+var_s0]
0x1400149e1  mov     rbx, [r11+28h]
0x1400149e5  mov     rsi, [r11+30h]
0x1400149e9  mov     rsp, r11
0x1400149ec  pop     r14
0x1400149ee  pop     rdi
0x1400149ef  pop     rbp
0x1400149f0  retn
```
