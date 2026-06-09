# Kerb3961::RC4_4757::DeriveSpecificKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::KeyUsage,Kerb3961::SpecificKeyScenario)

- ea: `0x18000f5e0`
- end: `0x18000f71b`
- name: `?DeriveSpecificKey@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@W4KeyUsage@2@W4SpecificKeyScenario@2@@Z`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003a54`
- `0x18000f5e0`
- `0x180011760`
- `0x1800118cc`
- `0x180011ab8`
- `0x180011b40`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::DeriveSpecificKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v8; // rax
  const char *v9; // rdx
  char *v10; // rdi
  __int64 v11; // rax
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  int v17; // esi
  __int64 v18; // rcx
  _BYTE v20[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v21; // [rsp+28h] [rbp-40h]

  v8 = (char *)operator new[](0x20u, (const struct std::nothrow_t *)a2);
  v10 = v8;
  if ( v8 )
  {
    *(_QWORD *)(v8 + 20) = 0;
    *((_DWORD *)v8 + 7) = 0;
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    *((_DWORD *)v8 + 4) = -1073741823;
    v11 = Kerb3961::CopyBuffer((__int64)v20, a3);
    v13 = *((_QWORD *)v10 + 1);
    v14 = v11;
    if ( v13 )
      Kerb3961Free(v13);
    *(_QWORD *)v10 = *(_QWORD *)v14;
    v15 = *(_QWORD *)(v14 + 8);
    *(_QWORD *)v14 = 0;
    *((_QWORD *)v10 + 1) = v15;
    v16 = *(_DWORD *)(v14 + 16);
    *(_QWORD *)(v14 + 8) = 0;
    *((_DWORD *)v10 + 4) = v16;
    *(_DWORD *)(v14 + 16) = -1073741823;
    if ( v21 )
      Kerb3961Free(v21);
    v17 = *((_DWORD *)v10 + 4);
    if ( v17 >= 0 )
    {
      *((_QWORD *)v10 + 3) = a4;
      if ( a4 == 3 )
        *((_QWORD *)v10 + 3) = 8;
      *(_QWORD *)a2 = a1;
      *(_QWORD *)(a2 + 8) = v10;
      *(_DWORD *)(a2 + 16) = 0;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"specificKey->key",
        (const char *)(unsigned int)v17,
        v12);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v17;
      v18 = *((_QWORD *)v10 + 1);
      if ( v18 )
        Kerb3961Free(v18);
      Kerb3961Free(v10);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"specificKey", v9);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f5e0  push    rbx
0x18000f5e2  push    rbp
0x18000f5e3  push    rsi
0x18000f5e4  push    rdi
0x18000f5e5  push    r14
0x18000f5e7  sub     rsp, 40h
0x18000f5eb  mov     r14, rcx
0x18000f5ee  mov     rbp, r9
0x18000f5f1  mov     ecx, 20h ; ' '; unsigned __int64
0x18000f5f6  mov     rsi, r8
0x18000f5f9  mov     rbx, rdx
0x18000f5fc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f601  mov     rdi, rax
0x18000f604  test    rax, rax
0x18000f607  jz      loc_18000F6EA
0x18000f60d  mov     qword ptr [rax+14h], 0
0x18000f615  lea     rcx, [rsp+68h+var_48]
0x18000f61a  mov     dword ptr [rax+1Ch], 0
0x18000f621  mov     rdx, rsi
0x18000f624  mov     qword ptr [rax], 0
0x18000f62b  mov     qword ptr [rax+8], 0
0x18000f633  mov     dword ptr [rax+10h], 0C0000001h
0x18000f63a  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000f63f  mov     rcx, [rdi+8]
0x18000f643  mov     rsi, rax
0x18000f646  test    rcx, rcx
0x18000f649  jz      short loc_18000F650
0x18000f64b  call    Kerb3961Free
0x18000f650  mov     rcx, [rsi]
0x18000f653  mov     [rdi], rcx
0x18000f656  mov     rcx, [rsi+8]
0x18000f65a  mov     qword ptr [rsi], 0
0x18000f661  mov     [rdi+8], rcx
0x18000f665  mov     eax, [rsi+10h]
0x18000f668  mov     qword ptr [rsi+8], 0
0x18000f670  mov     [rdi+10h], eax
0x18000f673  mov     dword ptr [rsi+10h], 0C0000001h
0x18000f67a  mov     rcx, [rsp+68h+var_40]
0x18000f67f  test    rcx, rcx
0x18000f682  jz      short loc_18000F689
0x18000f684  call    Kerb3961Free
0x18000f689  mov     esi, [rdi+10h]
0x18000f68c  test    esi, esi
0x18000f68e  jns     short loc_18000F6C8
0x18000f690  mov     edx, esi; char *
0x18000f692  lea     rcx, aSpecifickeyKey; "specificKey->key"
0x18000f699  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f69e  mov     qword ptr [rbx], 0
0x18000f6a5  mov     qword ptr [rbx+8], 0
0x18000f6ad  mov     [rbx+10h], esi
0x18000f6b0  mov     rcx, [rdi+8]
0x18000f6b4  test    rcx, rcx
0x18000f6b7  jz      short loc_18000F6BE
0x18000f6b9  call    Kerb3961Free
0x18000f6be  mov     rcx, rdi
0x18000f6c1  call    Kerb3961Free
0x18000f6c6  jmp     short loc_18000F70C
0x18000f6c8  mov     [rdi+18h], rbp
0x18000f6cc  cmp     rbp, 3
0x18000f6d0  jnz     short loc_18000F6DA
0x18000f6d2  mov     qword ptr [rdi+18h], 8
0x18000f6da  mov     [rbx], r14
0x18000f6dd  mov     [rbx+8], rdi
0x18000f6e1  mov     dword ptr [rbx+10h], 0
0x18000f6e8  jmp     short loc_18000F70C
0x18000f6ea  lea     rcx, aSpecifickey; "specificKey"
0x18000f6f1  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f6f6  mov     qword ptr [rbx], 0
0x18000f6fd  mov     qword ptr [rbx+8], 0
0x18000f705  mov     dword ptr [rbx+10h], 0C0000017h
0x18000f70c  mov     rax, rbx
0x18000f70f  add     rsp, 40h
0x18000f713  pop     r14
0x18000f715  pop     rdi
0x18000f716  pop     rsi
0x18000f717  pop     rbp
0x18000f718  pop     rbx
0x18000f719  retn
```
