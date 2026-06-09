# CVaultCredElement::CreateCredElement(IVaultSchemaElement *,CVaultCredDataMap *,IVaultCredentialElement *,CVaultCredElement * *)

- ea: `0x180008994`
- end: `0x180008ac8`
- name: `?CreateCredElement@CVaultCredElement@@SAKPEAUIVaultSchemaElement@@PEAVCVaultCredDataMap@@PEAUIVaultCredentialElement@@PEAPEAV1@@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct IVaultSchemaElement *, struct CVaultCredDataMap *, struct IVaultCredentialElement *, struct CVaultCredElement **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008050`

## callees

- `0x180003140`
- `0x180008994`
- `0x180008c34`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800089cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800089cf`

## pseudocode

```c
__int64 __fastcall CVaultCredElement::CreateCredElement(
        struct IVaultSchemaElement *a1,
        struct CVaultCredDataMap *a2,
        struct IVaultCredentialElement *a3,
        struct CVaultCredElement **a4)
{
  char *v8; // rbx
  unsigned int v9; // edi
  void (__fastcall *v11)(HLOCAL); // [rsp+20h] [rbp-48h] BYREF
  char *v12; // [rsp+28h] [rbp-40h]
  int v13; // [rsp+30h] [rbp-38h]

  v12 = 0;
  v13 = 0;
  v11 = CVaultCredElement::FreeCredElement;
  v8 = (char *)LocalAlloc(0x40u, 0x40u);
  if ( v8 )
  {
    *(_QWORD *)v8 = &CVaultCredElement::`vftable';
    v8[56] = 0;
    *(_OWORD *)(v8 + 24) = 0;
    *(_OWORD *)(v8 + 40) = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v11);
    v12 = v8;
    v9 = CVaultCredElement::ConstructCredentialElement((CVaultCredElement *)v8, a1, a2, a3);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids, v9);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v11);
      return v9;
    }
    else
    {
      v12 = 0;
      *a4 = (struct CVaultCredElement *)v8;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v11);
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids, 14);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v11);
    return 14;
  }
}

```

## disassembly

```asm
0x180008994  push    rbx
0x180008996  push    rbp
0x180008997  push    rsi
0x180008998  push    rdi
0x180008999  push    r14
0x18000899b  sub     rsp, 40h
0x18000899f  mov     rsi, r9
0x1800089a2  mov     rdi, r8
0x1800089a5  mov     rbp, rdx
0x1800089a8  mov     r14, rcx
0x1800089ab  mov     [rsp+68h+var_40], 0
0x1800089b4  mov     [rsp+68h+var_38], 0
0x1800089bc  lea     rax, ?FreeCredElement@CVaultCredElement@@SAXPEAV1@@Z; CVaultCredElement::FreeCredElement(CVaultCredElement *)
0x1800089c3  mov     [rsp+68h+var_48], rax
0x1800089c8  mov     ecx, 40h ; '@'; uFlags
0x1800089cd  mov     edx, ecx; uBytes
0x1800089cf  call    cs:__imp_LocalAlloc
0x1800089d5  mov     rbx, rax
0x1800089d8  test    rax, rax
0x1800089db  jz      short loc_180008A40
0x1800089dd  lea     rax, ??_7CVaultCredElement@@6B@; const CVaultCredElement::`vftable'
0x1800089e4  mov     [rbx], rax
0x1800089e7  mov     byte ptr [rbx+38h], 0
0x1800089eb  xorps   xmm0, xmm0
0x1800089ee  movups  xmmword ptr [rbx+18h], xmm0
0x1800089f2  movups  xmmword ptr [rbx+28h], xmm0
0x1800089f6  lea     rcx, [rsp+68h+var_48]
0x1800089fb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180008a00  mov     [rsp+68h+var_40], rbx
0x180008a05  mov     r9, rdi; struct IVaultCredentialElement *
0x180008a08  mov     r8, rbp; struct CVaultCredDataMap *
0x180008a0b  mov     rdx, r14; struct IVaultSchemaElement *
0x180008a0e  mov     rcx, rbx; this
0x180008a11  call    ?ConstructCredentialElement@CVaultCredElement@@QEAAKPEAUIVaultSchemaElement@@PEAVCVaultCredDataMap@@PEAUIVaultCredentialElement@@@Z; CVaultCredElement::ConstructCredentialElement(IVaultSchemaElement *,CVaultCredDataMap *,IVaultCredentialElement *)
0x180008a16  mov     edi, eax
0x180008a18  test    eax, eax
0x180008a1a  jnz     short loc_180008A84
0x180008a1c  mov     [rsp+68h+var_40], 0
0x180008a25  mov     [rsi], rbx
0x180008a28  lea     rcx, [rsp+68h+var_48]
0x180008a2d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180008a32  nop
0x180008a33  xor     eax, eax
0x180008a35  add     rsp, 40h
0x180008a39  pop     r14
0x180008a3b  pop     rdi
0x180008a3c  pop     rsi
0x180008a3d  pop     rbp
0x180008a3e  pop     rbx
0x180008a3f  retn
0x180008a40  lea     rax, WPP_GLOBAL_Control
0x180008a47  mov     ebx, 0Eh
0x180008a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a53  cmp     rcx, rax
0x180008a56  jz      short loc_180008A75
0x180008a58  test    byte ptr [rcx+1Ch], 2
0x180008a5c  jz      short loc_180008A75
0x180008a5e  lea     edx, [rbx-4]
0x180008a61  mov     r9d, ebx
0x180008a64  lea     r8, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids
0x180008a6b  mov     rcx, [rcx+10h]
0x180008a6f  call    WPP_SF_d
0x180008a74  nop
0x180008a75  lea     rcx, [rsp+68h+var_48]
0x180008a7a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180008a7f  nop
0x180008a80  mov     eax, ebx
0x180008a82  jmp     short loc_180008A35
0x180008a84  lea     rax, WPP_GLOBAL_Control
0x180008a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a92  cmp     rcx, rax
0x180008a95  jz      short loc_180008AB6
0x180008a97  test    byte ptr [rcx+1Ch], 2
0x180008a9b  jz      short loc_180008AB6
0x180008a9d  mov     edx, 0Bh
0x180008aa2  mov     r9d, edi
0x180008aa5  lea     r8, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids
0x180008aac  mov     rcx, [rcx+10h]
0x180008ab0  call    WPP_SF_d
0x180008ab5  nop
0x180008ab6  lea     rcx, [rsp+68h+var_48]
0x180008abb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180008ac0  nop
0x180008ac1  mov     eax, edi
0x180008ac3  jmp     loc_180008A35
```
