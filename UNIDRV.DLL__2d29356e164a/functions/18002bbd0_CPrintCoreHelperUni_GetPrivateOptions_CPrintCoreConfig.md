# CPrintCoreHelperUni::GetPrivateOptions(CPrintCoreConfig *)

- ea: `0x18002bbd0`
- end: `0x18002bd6a`
- name: `?GetPrivateOptions@CPrintCoreHelperUni@@MEAAPEAUtagPrivateFeaturesAccessTable@@PEAVCPrintCoreConfig@@@Z`
- size: `410`
- prototype: `struct tagPrivateFeaturesAccessTable *(CPrintCoreHelperUni *__hidden this, struct CPrintCoreConfig *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18002bbd0`
- `0x18002c628`
- `0x18002c724`
- `0x180045b50`
- `0x180075010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18002bcd0`
- `KERNEL32!LocalAlloc` at `0x18002bcd0`

## pseudocode

```c
struct tagPrivateFeaturesAccessTable *__fastcall CPrintCoreHelperUni::GetPrivateOptions(
        CPrintCoreHelperUni *this,
        struct CPrintCoreConfig *a2)
{
  __int64 v5; // rbp
  __int64 v6; // rbp
  int v7; // ebx
  unsigned int PrinterHandle; // eax
  int v9; // r9d
  unsigned int v10; // r9d
  unsigned int v11; // r8d
  unsigned int v12; // eax
  _QWORD *v13; // rax
  unsigned int v14; // r8d
  char *v15; // rcx
  __int64 v16; // rdx
  int v17; // [rsp+60h] [rbp+8h] BYREF

  if ( !(*(unsigned int (__fastcall **)(_QWORD))(*((_QWORD *)this + 134) + 16LL))(*(_QWORD *)a2) )
    return 0;
  if ( !*((_QWORD *)this + 147) )
  {
    v17 = 0;
    if ( *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 54) )
    {
      v5 = *((unsigned int *)CPrintCoreConfig::GetUIInfo(a2) + 54);
      v6 = *((_QWORD *)CPrintCoreConfig::GetUIInfo(a2) + 41) + v5;
    }
    else
    {
      v6 = 0;
    }
    v7 = *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 75);
    PrinterHandle = (unsigned int)CPrintCoreConfig::GetPrinterHandle(a2);
    VGetEnabledEMFFeatures(PrinterHandle, v7, v6 != 0, v9, (__int64)&v17);
    v10 = 0;
    v11 = 48;
    if ( (_DWORD)gpUnidrvEMFFeatures )
    {
      do
      {
        v12 = v11 + 24;
        if ( (v17 & *(_DWORD *)(&gpUnidrvEMFFeatures + 4 * v10)) != *((_DWORD *)&gpUnidrvEMFFeatures + 8 * v10) )
          v12 = v11;
        ++v10;
        v11 = v12;
      }
      while ( *((_DWORD *)&gpUnidrvEMFFeatures + 8 * v10) );
    }
    v13 = LocalAlloc(0x40u, v11);
    *((_QWORD *)this + 147) = v13;
    if ( v13 )
    {
      v14 = 0;
      v15 = (char *)(v13 + 3);
      *(_OWORD *)v13 = *(_OWORD *)&gpUnidrvPrivateFeaturesTable;
      v13[2] = off_180090A08;
      if ( (_DWORD)gpUnidrvEMFFeatures )
      {
        do
        {
          v16 = 32LL * v14;
          if ( (v17 & *(_DWORD *)((_BYTE *)&gpUnidrvEMFFeatures + v16)) == *(_DWORD *)((char *)&gpUnidrvEMFFeatures + v16) )
          {
            *(_OWORD *)v15 = *(_OWORD *)((char *)&gpUnidrvEMFFeatures + v16 + 8);
            *((_QWORD *)v15 + 2) = *(struct _unnamed_type_gpUnidrvEMFFeatures_ near **)((char *)&gpUnidrvEMFFeatures
                                                                                      + v16
                                                                                      + 24);
            v15 += 24;
          }
          ++v14;
        }
        while ( *((_DWORD *)&gpUnidrvEMFFeatures + 8 * v14) );
      }
      *(_OWORD *)v15 = *(_OWORD *)&gpUnidrvPrivateFeaturesTerminator;
      *((_QWORD *)v15 + 2) = qword_180091630;
    }
  }
  return (struct tagPrivateFeaturesAccessTable *)*((_QWORD *)this + 147);
}

```

## disassembly

```asm
0x18002bbd0  push    rbx
0x18002bbd2  push    rbp
0x18002bbd3  push    rsi
0x18002bbd4  push    rdi
0x18002bbd5  sub     rsp, 38h
0x18002bbd9  mov     rax, [rcx+430h]
0x18002bbe0  mov     rsi, rcx
0x18002bbe3  mov     rcx, [rdx]
0x18002bbe6  mov     rdi, rdx
0x18002bbe9  mov     rax, [rax+10h]
0x18002bbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbf2  test    eax, eax
0x18002bbf4  jz      short loc_18002BC10
0x18002bbf6  cmp     qword ptr [rsi+498h], 0
0x18002bbfe  jz      short loc_18002BC14
0x18002bc00  mov     rax, [rsi+498h]
0x18002bc07  add     rsp, 38h
0x18002bc0b  pop     rdi
0x18002bc0c  pop     rsi
0x18002bc0d  pop     rbp
0x18002bc0e  pop     rbx
0x18002bc0f  retn
0x18002bc10  xor     eax, eax
0x18002bc12  jmp     short loc_18002BC07
0x18002bc14  mov     rcx, rdi; this
0x18002bc17  mov     [rsp+58h+arg_0], 0
0x18002bc1f  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002bc24  cmp     dword ptr [rax+0D8h], 0
0x18002bc2b  jz      loc_18002BD63
0x18002bc31  mov     rcx, rdi; this
0x18002bc34  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002bc39  mov     rcx, rdi; this
0x18002bc3c  mov     ebp, [rax+0D8h]
0x18002bc42  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002bc47  add     rbp, [rax+148h]
0x18002bc4e  mov     rcx, rdi; this
0x18002bc51  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002bc56  mov     rcx, rdi; this
0x18002bc59  mov     ebx, [rax+12Ch]
0x18002bc5f  call    ?GetPrinterHandle@CPrintCoreConfig@@QEBAPEAXXZ; CPrintCoreConfig::GetPrinterHandle(void)
0x18002bc64  xor     r8d, r8d
0x18002bc67  lea     rcx, [rsp+58h+arg_0]
0x18002bc6c  mov     [rsp+58h+var_38], rcx
0x18002bc71  test    rbp, rbp
0x18002bc74  mov     edx, ebx
0x18002bc76  mov     rcx, rax
0x18002bc79  setnz   r8b
0x18002bc7d  call    VGetEnabledEMFFeatures
0x18002bc82  xor     r9d, r9d
0x18002bc85  lea     rbx, ?gpUnidrvEMFFeatures@@3PAU_unnamed_type_gpUnidrvEMFFeatures_@@A; _unnamed_type_gpUnidrvEMFFeatures_ near * gpUnidrvEMFFeatures
0x18002bc8c  cmp     cs:?gpUnidrvEMFFeatures@@3PAU_unnamed_type_gpUnidrvEMFFeatures_@@A, r9d; _unnamed_type_gpUnidrvEMFFeatures_ near * gpUnidrvEMFFeatures
0x18002bc93  mov     r8d, 30h ; '0'
0x18002bc99  jz      short loc_18002BCC8
0x18002bc9b  mov     eax, r9d
0x18002bc9e  shl     rax, 5
0x18002bca2  mov     edx, [rax+rbx]
0x18002bca5  lea     eax, [r8+18h]
0x18002bca9  mov     ecx, edx
0x18002bcab  and     ecx, [rsp+58h+arg_0]
0x18002bcaf  cmp     ecx, edx
0x18002bcb1  cmovnz  eax, r8d
0x18002bcb5  inc     r9d
0x18002bcb8  mov     r8d, eax
0x18002bcbb  mov     eax, r9d
0x18002bcbe  shl     rax, 5
0x18002bcc2  cmp     dword ptr [rax+rbx], 0
0x18002bcc6  jnz     short loc_18002BC9B
0x18002bcc8  mov     edx, r8d; uBytes
0x18002bccb  mov     ecx, 40h ; '@'; uFlags
0x18002bcd0  call    cs:__imp_LocalAlloc
0x18002bcd6  mov     [rsi+498h], rax
0x18002bcdd  test    rax, rax
0x18002bce0  jz      loc_18002BC00
0x18002bce6  movups  xmm0, xmmword ptr cs:?gpUnidrvPrivateFeaturesTable@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpUnidrvPrivateFeaturesTable
0x18002bced  xor     r8d, r8d
0x18002bcf0  lea     rcx, [rax+18h]
0x18002bcf4  movups  xmmword ptr [rax], xmm0
0x18002bcf7  movsd   xmm1, cs:off_180090A08
0x18002bcff  movsd   qword ptr [rax+10h], xmm1
0x18002bd04  cmp     cs:?gpUnidrvEMFFeatures@@3PAU_unnamed_type_gpUnidrvEMFFeatures_@@A, r8d; _unnamed_type_gpUnidrvEMFFeatures_ near * gpUnidrvEMFFeatures
0x18002bd0b  jz      short loc_18002BD47
0x18002bd0d  mov     edx, r8d
0x18002bd10  shl     rdx, 5
0x18002bd14  mov     eax, [rdx+rbx]
0x18002bd17  and     eax, [rsp+58h+arg_0]
0x18002bd1b  cmp     eax, [rdx+rbx]
0x18002bd1e  jnz     short loc_18002BD37
0x18002bd20  movups  xmm0, xmmword ptr [rdx+rbx+8]
0x18002bd25  movups  xmmword ptr [rcx], xmm0
0x18002bd28  movsd   xmm1, qword ptr [rdx+rbx+18h]
0x18002bd2e  movsd   qword ptr [rcx+10h], xmm1
0x18002bd33  add     rcx, 18h
0x18002bd37  inc     r8d
0x18002bd3a  mov     eax, r8d
0x18002bd3d  shl     rax, 5
0x18002bd41  cmp     dword ptr [rax+rbx], 0
0x18002bd45  jnz     short loc_18002BD0D
0x18002bd47  movups  xmm0, cs:?gpUnidrvPrivateFeaturesTerminator@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpUnidrvPrivateFeaturesTerminator
0x18002bd4e  movups  xmmword ptr [rcx], xmm0
0x18002bd51  movsd   xmm1, cs:qword_180091630
0x18002bd59  movsd   qword ptr [rcx+10h], xmm1
0x18002bd5e  jmp     loc_18002BC00
0x18002bd63  xor     ebp, ebp
0x18002bd65  jmp     loc_18002BC4E
```
