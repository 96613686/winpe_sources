# ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)

- ea: `0x18004a8fc`
- end: `0x18004aa57`
- name: `?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, const struct IdDescription *, struct ISyncKnowledge *)`
- caller_count: `10`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180029810`
- `0x180047350`
- `0x180047530`
- `0x180047900`
- `0x180047a60`
- `0x180048bd0`
- `0x180049520`
- `0x180049c00`
- `0x18004a070`
- `0x18004a7f0`

## callees

- `0x180005e8c`
- `0x18001a038`
- `0x18001ae20`
- `0x18001f730`
- `0x18004a8fc`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x18004a945`: `ChangeApplicationServices::ValidateIdParameters`
- `0x18004aa11`: `ChangeApplicationServices::ValidateIdParameters`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ValidateIdParameters(
        ChangeApplicationServices *this,
        const struct IdDescription *a2,
        struct ISyncKnowledge *a3)
{
  struct ISyncKnowledgeVtbl *lpVtbl; // rax
  int v6; // ebx
  __int64 v8; // [rsp+30h] [rbp-50h] BYREF
  int v9; // [rsp+38h] [rbp-48h] BYREF
  __int16 v10; // [rsp+3Ch] [rbp-44h]
  int v11; // [rsp+40h] [rbp-40h]
  __int16 v12; // [rsp+44h] [rbp-3Ch]
  int v13; // [rsp+48h] [rbp-38h]
  __int16 v14; // [rsp+4Ch] [rbp-34h]
  int v15; // [rsp+50h] [rbp-30h] BYREF
  __int128 v16; // [rsp+54h] [rbp-2Ch]
  __int64 v17; // [rsp+64h] [rbp-1Ch]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ValidateIdParameters");
  }
  lpVtbl = a3->lpVtbl;
  v8 = 0;
  v6 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a3,
         &GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8,
         &v8);
  v15 = 28;
  v17 = 0;
  v16 = 0;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 216LL))(v8, &v15);
    if ( v6 >= 0 )
    {
      v9 = v16;
      v10 = WORD2(v16);
      v11 = DWORD2(v16);
      v12 = WORD6(v16);
      v13 = v17;
      v14 = WORD2(v17);
      if ( (unsigned int)IdDescription::operator!=(a2, &v9) )
        v6 = -2147217408;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ValidateIdParameters",
      v6);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004a8fc  mov     [rsp-18h+arg_0], rbx
0x18004a901  push    rbp
0x18004a902  push    rsi
0x18004a903  push    rdi
0x18004a904  mov     rbp, rsp
0x18004a907  sub     rsp, 80h
0x18004a90e  mov     rax, cs:__security_cookie
0x18004a915  xor     rax, rsp
0x18004a918  mov     [rbp+var_10], rax
0x18004a91c  mov     rbx, r8
0x18004a91f  mov     rdi, rdx
0x18004a922  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a929  lea     rsi, WPP_GLOBAL_Control
0x18004a930  cmp     rcx, rsi
0x18004a933  jz      short loc_18004A95D
0x18004a935  test    byte ptr [rcx+1Ch], 80h
0x18004a939  jz      short loc_18004A95D
0x18004a93b  cmp     byte ptr [rcx+19h], 5
0x18004a93f  jb      short loc_18004A95D
0x18004a941  mov     rcx, [rcx+10h]
0x18004a945  lea     r9, aChangeapplicat_35; "ChangeApplicationServices::ValidateIdPa"...
0x18004a94c  mov     edx, 3Ch ; '<'
0x18004a951  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a958  call    WPP_SF_s
0x18004a95d  mov     rax, [rbx]
0x18004a960  lea     r8, [rbp+var_50]
0x18004a964  lea     rdx, _GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8
0x18004a96b  mov     [rbp+var_50], 0
0x18004a973  mov     rcx, rbx
0x18004a976  mov     rax, [rax]
0x18004a979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a97e  mov     ebx, eax
0x18004a980  mov     [rbp+var_30], 1Ch
0x18004a987  xor     eax, eax
0x18004a989  xorps   xmm0, xmm0
0x18004a98c  mov     [rbp+var_1C], rax
0x18004a990  movups  [rbp+var_2C], xmm0
0x18004a994  test    ebx, ebx
0x18004a996  js      short loc_18004A9F5
0x18004a998  mov     rcx, [rbp+var_50]
0x18004a99c  lea     rdx, [rbp+var_30]
0x18004a9a0  mov     rax, [rcx]
0x18004a9a3  mov     rax, [rax+0D8h]
0x18004a9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9af  mov     ebx, eax
0x18004a9b1  test    eax, eax
0x18004a9b3  js      short loc_18004A9F5
0x18004a9b5  mov     eax, dword ptr [rbp+var_2C]
0x18004a9b8  lea     rdx, [rbp+var_48]
0x18004a9bc  mov     [rbp+var_48], eax
0x18004a9bf  mov     rcx, rdi
0x18004a9c2  movzx   eax, word ptr [rbp+var_2C+4]
0x18004a9c6  mov     [rbp+var_44], ax
0x18004a9ca  mov     eax, dword ptr [rbp+var_2C+8]
0x18004a9cd  mov     [rbp+var_40], eax
0x18004a9d0  movzx   eax, word ptr [rbp+var_2C+0Ch]
0x18004a9d4  mov     [rbp+var_3C], ax
0x18004a9d8  mov     eax, dword ptr [rbp+var_1C]
0x18004a9db  mov     [rbp+var_38], eax
0x18004a9de  movzx   eax, word ptr [rbp+var_1C+4]
0x18004a9e2  mov     [rbp+var_34], ax
0x18004a9e6  call    ??9IdDescription@@QEBAHAEBU0@@Z; IdDescription::operator!=(IdDescription const &)
0x18004a9eb  test    eax, eax
0x18004a9ed  mov     ecx, 80041000h
0x18004a9f2  cmovnz  ebx, ecx
0x18004a9f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a9fc  cmp     rcx, rsi
0x18004a9ff  jz      short loc_18004AA2D
0x18004aa01  test    byte ptr [rcx+1Ch], 80h
0x18004aa05  jz      short loc_18004AA2D
0x18004aa07  cmp     byte ptr [rcx+19h], 5
0x18004aa0b  jb      short loc_18004AA2D
0x18004aa0d  mov     rcx, [rcx+10h]
0x18004aa11  lea     r9, aChangeapplicat_35; "ChangeApplicationServices::ValidateIdPa"...
0x18004aa18  mov     edx, 3Dh ; '='
0x18004aa1d  mov     [rsp+80h+var_60], ebx
0x18004aa21  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004aa28  call    WPP_SF_sD
0x18004aa2d  lea     rcx, [rbp+var_50]
0x18004aa31  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004aa36  mov     eax, ebx
0x18004aa38  mov     rcx, [rbp+var_10]
0x18004aa3c  xor     rcx, rsp; StackCookie
0x18004aa3f  call    __security_check_cookie
0x18004aa44  mov     rbx, [rsp+80h+arg_0]
0x18004aa4c  add     rsp, 80h
0x18004aa53  pop     rdi
0x18004aa54  pop     rsi
0x18004aa55  pop     rbp
0x18004aa56  retn
```
