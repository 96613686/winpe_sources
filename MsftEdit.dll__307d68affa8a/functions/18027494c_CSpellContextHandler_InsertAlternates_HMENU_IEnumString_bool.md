# CSpellContextHandler::InsertAlternates(HMENU__ *,IEnumString *,bool)

- ea: `0x18027494c`
- end: `0x180274c69`
- name: `?InsertAlternates@CSpellContextHandler@@AEAAJPEAUHMENU__@@PEAUIEnumString@@_N@Z`
- size: `797`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this, HMENU, struct IEnumString *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180275934`
- `0x180275d5c`

## callees

- `0x180048d5c`
- `0x180273cc4`
- `0x180273e68`
- `0x180273efc`
- `0x180273fb0`
- `0x18027494c`
- `0x180274c70`
- `0x180274d08`
- `0x180274e38`
- `0x180274ea0`
- `0x18027a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180274ab8`
- `OLEAUT32!__imp_SysFreeString` at `0x180274ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274a8b`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::InsertAlternates(
        CSpellContextHandler *this,
        HMENU a2,
        struct IEnumString *a3,
        char a4)
{
  __int64 v7; // rcx
  int Command; // ebx
  unsigned int v9; // esi
  struct IEnumStringVtbl *lpVtbl; // rax
  __int64 v11; // r12
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  UINT v13; // esi
  bool inserted; // bl
  unsigned int v15; // esi
  __int64 v16; // rdx
  bool v17; // al
  HMENU LanguageSubmenu; // rax
  unsigned int v20; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  char v23; // [rsp+90h] [rbp+40h] BYREF
  char v24; // [rsp+98h] [rbp+48h]

  v24 = a4;
  if ( !a3 )
  {
    v7 = *((_QWORD *)this + 6);
    if ( v7 )
      goto LABEL_5;
    return 2147549183LL;
  }
  if ( *((_QWORD *)this + 6) )
    return 2147549183LL;
  v7 = 0;
LABEL_5:
  Command = 0;
  v20 = *((_DWORD *)this + 18) - *((_DWORD *)this + 16) + 1;
  if ( v7 )
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 40LL))(v7, &v20);
  v9 = *((_DWORD *)this + 16);
  v23 = 0;
  while ( v9 <= *((_DWORD *)this + 18) )
  {
    pv[0] = 0;
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      LODWORD(v21) = 0;
      Command = ((__int64 (__fastcall *)(struct IEnumString *, __int64, LPVOID *, __int64 *))lpVtbl->Next)(
                  a3,
                  1,
                  pv,
                  &v21);
    }
    else
    {
      v11 = *((_QWORD *)this + 6);
      if ( v11 )
      {
        v21 = 0;
        v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 32LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        Command = v12(v11, v9 - *((_DWORD *)this + 16), &v21);
        if ( Command >= 0 )
          Command = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v21 + 24LL))(v21, pv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      }
    }
    if ( Command < 0 )
      goto LABEL_28;
    if ( !pv[0] )
      break;
    if ( a2 )
    {
      if ( !CSpellContextHandler::InsertMenuItemFromString(
              a2,
              v9 - *((_DWORD *)this + 16),
              (unsigned __int16 *)pv[0],
              v9) )
        goto LABEL_19;
LABEL_24:
      v23 = 1;
      goto LABEL_20;
    }
    if ( !*((_QWORD *)this + 18) )
    {
LABEL_19:
      Command = -2147418113;
      goto LABEL_20;
    }
    Command = CSpellContextHandler::CreateCommand(this, (PCWSTR)pv[0], v9);
    if ( Command >= 0 )
      goto LABEL_24;
LABEL_20:
    if ( a3 )
      CoTaskMemFree(pv[0]);
    else
      SysFreeString((BSTR)pv[0]);
    if ( Command >= 0 )
      ++v9;
LABEL_28:
    if ( v20 < v9 - *((_DWORD *)this + 16) + 1 || Command < 0 )
      break;
  }
  v13 = v9 - *((_DWORD *)this + 16);
  if ( !v23 )
    goto LABEL_37;
  if ( Command < 0 )
    return (unsigned int)Command;
  if ( a2 )
  {
    if ( CSpellContextHandler::InsertSeparator(a2, v13) )
    {
      ++v13;
      goto LABEL_37;
    }
    return (unsigned int)Command;
  }
  if ( !*((_QWORD *)this + 18) )
    return (unsigned int)-2147418113;
  Command = CSpellContextHandler::CreateCommandSeparator(this);
LABEL_37:
  if ( Command >= 0 )
  {
    if ( a2 )
    {
      inserted = CSpellContextHandler::InsertMenuItemFromResource(
                   this,
                   a2,
                   v13,
                   *((_DWORD *)this + 25),
                   *((_DWORD *)this + 21));
      if ( inserted )
      {
        v15 = v13 + 1;
        if ( *((_BYTE *)this + 158) )
          goto LABEL_47;
        inserted = CSpellContextHandler::InsertMenuItemFromResource(
                     this,
                     a2,
                     v15,
                     *((_DWORD *)this + 26),
                     *((_DWORD *)this + 22));
        v23 = 0;
        ++v15;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 256LL))(
               *(_QWORD *)(*((_QWORD *)this + 3) + 72LL),
               &v23) )
        {
          if ( v23 )
          {
            v17 = CSpellContextHandler::InsertMenuItemFromResource(
                    this,
                    a2,
                    v15,
                    *((_DWORD *)this + 34),
                    *((_DWORD *)this + 23));
          }
          else
          {
            LanguageSubmenu = CSpellContextHandler::CreateLanguageSubmenu(this, v16);
            v17 = CSpellContextHandler::InsertSubMenuFromResource(
                    this,
                    a2,
                    v15,
                    *((_DWORD *)this + 31),
                    LanguageSubmenu);
          }
          ++v15;
          inserted = v17;
        }
        if ( inserted )
        {
LABEL_47:
          if ( v24 )
            inserted = CSpellContextHandler::InsertSeparator(a2, v15);
        }
      }
      return !inserted ? 0x8000FFFF : 0;
    }
    if ( *((_QWORD *)this + 18) )
    {
      Command = CSpellContextHandler::CreateCommandFromResource(this, *((_DWORD *)this + 25), *((_DWORD *)this + 21));
      if ( Command >= 0 && !*((_BYTE *)this + 158) )
        return (unsigned int)CSpellContextHandler::CreateCommandFromResource(
                               this,
                               *((_DWORD *)this + 26),
                               *((_DWORD *)this + 22));
      return (unsigned int)Command;
    }
    return (unsigned int)-2147418113;
  }
  return (unsigned int)Command;
}

```

## disassembly

```asm
0x18027494c  mov     [rsp-28h+arg_0], rbx
0x180274951  mov     [rsp-28h+arg_8], rsi
0x180274956  mov     [rsp-28h+arg_18], r9b
0x18027495b  push    rbp
0x18027495c  push    rdi
0x18027495d  push    r12
0x18027495f  push    r13
0x180274961  push    r14
0x180274963  mov     rbp, rsp
0x180274966  sub     rsp, 50h
0x18027496a  mov     r13, r8
0x18027496d  mov     r14, rdx
0x180274970  mov     rdi, rcx
0x180274973  test    r8, r8
0x180274976  jz      short loc_180274987
0x180274978  cmp     qword ptr [rcx+30h], 0
0x18027497d  jnz     loc_180274C4B
0x180274983  xor     ecx, ecx
0x180274985  jmp     short loc_180274994
0x180274987  mov     rcx, [rcx+30h]
0x18027498b  test    rcx, rcx
0x18027498e  jz      loc_180274C4B
0x180274994  mov     eax, [rdi+48h]
0x180274997  xor     ebx, ebx
0x180274999  sub     eax, [rdi+40h]
0x18027499c  inc     eax
0x18027499e  mov     [rbp+var_20], eax
0x1802749a1  test    rcx, rcx
0x1802749a4  jz      short loc_1802749B6
0x1802749a6  mov     rax, [rcx]
0x1802749a9  lea     rdx, [rbp+var_20]
0x1802749ad  mov     rax, [rax+28h]
0x1802749b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802749b6  mov     esi, [rdi+40h]
0x1802749b9  xor     al, al
0x1802749bb  mov     [rbp+arg_10], al
0x1802749be  cmp     esi, [rdi+48h]
0x1802749c1  ja      loc_180274AD8
0x1802749c7  mov     [rbp+pv], 0
0x1802749cf  test    r13, r13
0x1802749d2  jz      short loc_1802749FC
0x1802749d4  mov     rax, [r13+0]
0x1802749d8  lea     r9, [rbp+var_18]
0x1802749dc  lea     r8, [rbp+pv]
0x1802749e0  mov     dword ptr [rbp+var_18], 0
0x1802749e7  mov     edx, 1
0x1802749ec  mov     rcx, r13
0x1802749ef  mov     rax, [rax+18h]
0x1802749f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802749f8  mov     ebx, eax
0x1802749fa  jmp     short loc_180274A57
0x1802749fc  mov     r12, [rdi+30h]
0x180274a00  test    r12, r12
0x180274a03  jz      short loc_180274A57
0x180274a05  mov     [rbp+var_18], 0
0x180274a0d  lea     rcx, [rbp+var_18]
0x180274a11  mov     rax, [r12]
0x180274a15  mov     rbx, [rax+20h]
0x180274a19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180274a1e  mov     edx, esi
0x180274a20  lea     r8, [rbp+var_18]
0x180274a24  sub     edx, [rdi+40h]
0x180274a27  mov     rcx, r12
0x180274a2a  mov     rax, rbx
0x180274a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274a32  mov     ebx, eax
0x180274a34  test    eax, eax
0x180274a36  js      short loc_180274A4E
0x180274a38  mov     rcx, [rbp+var_18]
0x180274a3c  lea     rdx, [rbp+pv]
0x180274a40  mov     rax, [rcx]
0x180274a43  mov     rax, [rax+18h]
0x180274a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274a4c  mov     ebx, eax
0x180274a4e  lea     rcx, [rbp+var_18]
0x180274a52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180274a57  test    ebx, ebx
0x180274a59  js      short loc_180274AC4
0x180274a5b  mov     r8, [rbp+pv]; unsigned __int16 *
0x180274a5f  test    r8, r8
0x180274a62  jz      short loc_180274AD8
0x180274a64  test    r14, r14
0x180274a67  jz      short loc_180274A93
0x180274a69  mov     edx, esi
0x180274a6b  mov     r9d, esi; unsigned int
0x180274a6e  sub     edx, [rdi+40h]; item
0x180274a71  mov     rcx, r14; hmenu
0x180274a74  call    ?InsertMenuItemFromString@CSpellContextHandler@@CA_NPEAUHMENU__@@IPEAGI@Z; CSpellContextHandler::InsertMenuItemFromString(HMENU__ *,uint,ushort *,uint)
0x180274a79  test    al, al
0x180274a7b  jnz     short loc_180274AB2
0x180274a7d  mov     ebx, 8000FFFFh
0x180274a82  mov     rcx, [rbp+pv]; bstrString
0x180274a86  test    r13, r13
0x180274a89  jz      short loc_180274AB8
0x180274a8b  call    cs:__imp_CoTaskMemFree
0x180274a91  jmp     short loc_180274ABE
0x180274a93  cmp     qword ptr [rdi+90h], 0
0x180274a9b  jz      short loc_180274A7D
0x180274a9d  mov     rdx, [rbp+pv]; sourceString
0x180274aa1  mov     r8d, esi; unsigned int
0x180274aa4  mov     rcx, rdi; this
0x180274aa7  call    ?CreateCommand@CSpellContextHandler@@AEAAJPEBGH@Z; CSpellContextHandler::CreateCommand(ushort const *,int)
0x180274aac  mov     ebx, eax
0x180274aae  test    eax, eax
0x180274ab0  js      short loc_180274A82
0x180274ab2  mov     [rbp+arg_10], 1
0x180274ab6  jmp     short loc_180274A82
0x180274ab8  call    cs:__imp_SysFreeString
0x180274abe  test    ebx, ebx
0x180274ac0  js      short loc_180274AC4
0x180274ac2  inc     esi
0x180274ac4  mov     eax, esi
0x180274ac6  sub     eax, [rdi+40h]
0x180274ac9  inc     eax
0x180274acb  cmp     [rbp+var_20], eax
0x180274ace  jb      short loc_180274AD8
0x180274ad0  test    ebx, ebx
0x180274ad2  jns     loc_1802749BE
0x180274ad8  sub     esi, [rdi+40h]
0x180274adb  cmp     [rbp+arg_10], 0
0x180274adf  jz      short loc_180274B1C
0x180274ae1  test    ebx, ebx
0x180274ae3  js      loc_180274C47
0x180274ae9  test    r14, r14
0x180274aec  jz      short loc_180274B04
0x180274aee  mov     edx, esi; item
0x180274af0  mov     rcx, r14; hmenu
0x180274af3  call    ?InsertSeparator@CSpellContextHandler@@CA_NPEAUHMENU__@@I@Z; CSpellContextHandler::InsertSeparator(HMENU__ *,uint)
0x180274af8  test    al, al
0x180274afa  jz      loc_180274C47
0x180274b00  inc     esi
0x180274b02  jmp     short loc_180274B1C
0x180274b04  cmp     qword ptr [rdi+90h], 0
0x180274b0c  jz      loc_180274C42
0x180274b12  mov     rcx, rdi; this
0x180274b15  call    ?CreateCommandSeparator@CSpellContextHandler@@AEAAJXZ; CSpellContextHandler::CreateCommandSeparator(void)
0x180274b1a  mov     ebx, eax
0x180274b1c  test    ebx, ebx
0x180274b1e  js      loc_180274C47
0x180274b24  test    r14, r14
0x180274b27  jz      loc_180274C07
0x180274b2d  mov     eax, [rdi+54h]
0x180274b30  mov     r8d, esi; unsigned int
0x180274b33  mov     r9d, [rdi+64h]; unsigned int
0x180274b37  mov     rdx, r14; HMENU
0x180274b3a  mov     rcx, rdi; this
0x180274b3d  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x180274b41  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x180274b46  mov     bl, al
0x180274b48  test    al, al
0x180274b4a  jz      loc_180274BF9
0x180274b50  inc     esi
0x180274b52  cmp     byte ptr [rdi+9Eh], 0
0x180274b59  jnz     loc_180274BE7
0x180274b5f  mov     eax, [rdi+58h]
0x180274b62  mov     r8d, esi; unsigned int
0x180274b65  mov     r9d, [rdi+68h]; unsigned int
0x180274b69  mov     rdx, r14; HMENU
0x180274b6c  mov     rcx, rdi; this
0x180274b6f  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x180274b73  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x180274b78  mov     bl, al
0x180274b7a  mov     [rbp+arg_10], 0
0x180274b7e  mov     rax, [rdi+18h]
0x180274b82  lea     rdx, [rbp+arg_10]
0x180274b86  inc     esi
0x180274b88  mov     rcx, [rax+48h]
0x180274b8c  mov     rax, [rcx]
0x180274b8f  mov     rax, [rax+100h]
0x180274b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274b9b  test    al, al
0x180274b9d  jz      short loc_180274BE3
0x180274b9f  cmp     [rbp+arg_10], 0
0x180274ba3  mov     rcx, rdi; this
0x180274ba6  jz      short loc_180274BC3
0x180274ba8  mov     eax, [rdi+5Ch]
0x180274bab  mov     r8d, esi; unsigned int
0x180274bae  mov     r9d, [rdi+88h]; unsigned int
0x180274bb5  mov     rdx, r14; HMENU
0x180274bb8  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x180274bbc  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x180274bc1  jmp     short loc_180274BDF
0x180274bc3  call    ?CreateLanguageSubmenu@CSpellContextHandler@@AEAAPEAUHMENU__@@XZ; CSpellContextHandler::CreateLanguageSubmenu(void)
0x180274bc8  mov     r9d, [rdi+7Ch]; unsigned int
0x180274bcc  mov     r8d, esi; unsigned int
0x180274bcf  mov     rdx, r14; HMENU
0x180274bd2  mov     [rsp+50h+var_30], rax; HMENU
0x180274bd7  mov     rcx, rdi; this
0x180274bda  call    ?InsertSubMenuFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@II0@Z; CSpellContextHandler::InsertSubMenuFromResource(HMENU__ *,uint,uint,HMENU__ *)
0x180274bdf  inc     esi
0x180274be1  mov     bl, al
0x180274be3  test    bl, bl
0x180274be5  jz      short loc_180274BF9
0x180274be7  cmp     [rbp+arg_18], 0
0x180274beb  jz      short loc_180274BF9
0x180274bed  mov     edx, esi; item
0x180274bef  mov     rcx, r14; hmenu
0x180274bf2  call    ?InsertSeparator@CSpellContextHandler@@CA_NPEAUHMENU__@@I@Z; CSpellContextHandler::InsertSeparator(HMENU__ *,uint)
0x180274bf7  mov     bl, al
0x180274bf9  neg     bl
0x180274bfb  sbb     ebx, ebx
0x180274bfd  not     ebx
0x180274bff  and     ebx, 8000FFFFh
0x180274c05  jmp     short loc_180274C47
0x180274c07  cmp     qword ptr [rdi+90h], 0
0x180274c0f  jz      short loc_180274C42
0x180274c11  mov     r8d, [rdi+54h]; unsigned int
0x180274c15  mov     rcx, rdi; this
0x180274c18  mov     edx, [rdi+64h]; uID
0x180274c1b  call    ?CreateCommandFromResource@CSpellContextHandler@@AEAAJIH@Z; CSpellContextHandler::CreateCommandFromResource(uint,int)
0x180274c20  mov     ebx, eax
0x180274c22  test    eax, eax
0x180274c24  js      short loc_180274C47
0x180274c26  cmp     byte ptr [rdi+9Eh], 0
0x180274c2d  jnz     short loc_180274C47
0x180274c2f  mov     r8d, [rdi+58h]; unsigned int
0x180274c33  mov     rcx, rdi; this
0x180274c36  mov     edx, [rdi+68h]; uID
0x180274c39  call    ?CreateCommandFromResource@CSpellContextHandler@@AEAAJIH@Z; CSpellContextHandler::CreateCommandFromResource(uint,int)
0x180274c3e  mov     ebx, eax
0x180274c40  jmp     short loc_180274C47
0x180274c42  mov     ebx, 8000FFFFh
0x180274c47  mov     eax, ebx
0x180274c49  jmp     short loc_180274C50
0x180274c4b  mov     eax, 8000FFFFh
0x180274c50  lea     r11, [rsp+50h+var_s0]
0x180274c55  mov     rbx, [r11+30h]
0x180274c59  mov     rsi, [r11+38h]
0x180274c5d  mov     rsp, r11
0x180274c60  pop     r14
0x180274c62  pop     r13
0x180274c64  pop     r12
0x180274c66  pop     rdi
0x180274c67  pop     rbp
0x180274c68  retn
```
