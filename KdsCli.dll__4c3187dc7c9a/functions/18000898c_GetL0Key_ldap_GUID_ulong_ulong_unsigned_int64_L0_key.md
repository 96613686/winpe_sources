# GetL0Key(ldap *,_GUID *,ulong,ulong,unsigned __int64,_L0_key * *)

- ea: `0x18000898c`
- end: `0x180008af4`
- name: `?GetL0Key@@YAJPEAUldap@@PEAU_GUID@@KK_KPEAPEAU_L0_key@@@Z`
- size: `360`
- prototype: `__int64 __usercall@<rax>(struct ldap *@<rcx>, UUID *Uuid@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int64, struct _L0_key **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008eb4`

## callees

- `0x1800038c0`
- `0x180004d5c`
- `0x18000898c`
- `0x180008afc`
- `0x180008cf0`
- `0x180009a14`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x1800089e7`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetL0Key(
        struct ldap *a1,
        UUID *Uuid,
        unsigned int a3,
        int a4,
        unsigned __int64 a5,
        struct _L0_key **a6)
{
  int MRKPath; // eax
  unsigned int v11; // ebx
  char v12; // r9
  char v13; // cl
  int v14; // edi
  struct _L0_key *v16; // [rsp+30h] [rbp-48h] BYREF
  void *lpMem; // [rsp+38h] [rbp-40h] BYREF

  lpMem = 0;
  v16 = 0;
  *a6 = 0;
  MRKPath = GetMRKPath(a1, (unsigned __int16 **)&lpMem);
  v11 = MRKPath;
  if ( MRKPath >= 0 )
  {
    if ( a4 )
    {
      v14 = a4 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
          v12 = -72;
LABEL_13:
          v11 = -2147024809;
          v13 = 87;
          goto LABEL_4;
        }
        MRKPath = GetL0KeyForSpecifiedIntervalLdap(a1, (unsigned __int16 *)lpMem, a3, a5, &v16);
        v11 = MRKPath;
        if ( MRKPath < 0 )
        {
          v12 = -78;
          goto LABEL_3;
        }
      }
      else
      {
        if ( !Uuid )
        {
          v12 = -103;
          goto LABEL_13;
        }
        MRKPath = GetSpecifiedL0KeyLdap(a1, (unsigned __int16 *)lpMem, Uuid, a3, a5, &v16);
        v11 = MRKPath;
        if ( MRKPath < 0 )
        {
          v12 = -91;
          goto LABEL_3;
        }
      }
    }
    else
    {
      MRKPath = GetLatestL0KeyLdap(a1, (unsigned __int16 *)lpMem, a3, &v16);
      v11 = MRKPath;
      if ( MRKPath < 0 )
      {
        v12 = -111;
        goto LABEL_3;
      }
    }
    *a6 = v16;
    v16 = 0;
    goto LABEL_19;
  }
  v12 = -127;
LABEL_3:
  v13 = MRKPath;
LABEL_4:
  SidKeyDebugTraceError(v13, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v12);
LABEL_19:
  FreeL0Key(v16);
  SIDKeyProvFree(lpMem);
  return v11;
}

```

## disassembly

```asm
0x18000898c  push    rbx
0x18000898e  push    rbp
0x18000898f  push    rdi
0x180008990  push    r12
0x180008992  push    r14
0x180008994  push    r15
0x180008996  sub     rsp, 48h
0x18000899a  mov     r12, [rsp+78h+arg_28]
0x1800089a2  mov     r15, rdx
0x1800089a5  lea     rdx, [rsp+78h+lpMem]; unsigned __int16 **
0x1800089aa  mov     [rsp+78h+lpMem], 0
0x1800089b3  mov     edi, r9d
0x1800089b6  mov     [rsp+78h+var_48], 0
0x1800089bf  mov     r14d, r8d
0x1800089c2  mov     rbp, rcx
0x1800089c5  mov     qword ptr [r12], 0
0x1800089cd  call    ?GetMRKPath@@YAJPEAUldap@@PEAPEAG@Z; GetMRKPath(ldap *,ushort * *)
0x1800089d2  mov     ebx, eax
0x1800089d4  test    eax, eax
0x1800089d6  jns     short loc_1800089F8
0x1800089d8  mov     r9d, 681h; unsigned int
0x1800089de  mov     ecx, eax; unsigned int
0x1800089e0  lea     rdx, aHr; "hr"
0x1800089e7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800089ee  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800089f3  jmp     loc_180008AD0
0x1800089f8  test    edi, edi
0x1800089fa  jz      loc_180008A98
0x180008a00  sub     edi, 1
0x180008a03  jz      short loc_180008A46
0x180008a05  cmp     edi, 1
0x180008a08  jz      short loc_180008A12
0x180008a0a  mov     r9d, 6B8h
0x180008a10  jmp     short loc_180008A51
0x180008a12  mov     r9, [rsp+78h+arg_20]; unsigned __int64
0x180008a1a  lea     rax, [rsp+78h+var_48]
0x180008a1f  mov     rdx, [rsp+78h+lpMem]; unsigned __int16 *
0x180008a24  mov     r8d, r14d; unsigned int
0x180008a27  mov     rcx, rbp; ld
0x180008a2a  mov     [rsp+78h+var_58], rax; struct _L0_key **
0x180008a2f  call    ?GetL0KeyForSpecifiedIntervalLdap@@YAJPEAUldap@@PEAGK_KPEAPEAU_L0_key@@@Z; GetL0KeyForSpecifiedIntervalLdap(ldap *,ushort *,ulong,unsigned __int64,_L0_key * *)
0x180008a34  mov     ebx, eax
0x180008a36  test    eax, eax
0x180008a38  jns     loc_180008ABE
0x180008a3e  mov     r9d, 6B2h
0x180008a44  jmp     short loc_1800089DE
0x180008a46  test    r15, r15
0x180008a49  jnz     short loc_180008A5D
0x180008a4b  mov     r9d, 699h
0x180008a51  mov     ebx, 80070057h
0x180008a56  mov     ecx, 80070057h
0x180008a5b  jmp     short loc_1800089E0
0x180008a5d  mov     rdx, [rsp+78h+lpMem]; unsigned __int16 *
0x180008a62  lea     rax, [rsp+78h+var_48]
0x180008a67  mov     [rsp+78h+var_50], rax; struct _L0_key **
0x180008a6c  mov     r9d, r14d; unsigned int
0x180008a6f  mov     rax, [rsp+78h+arg_20]
0x180008a77  mov     r8, r15; Uuid
0x180008a7a  mov     rcx, rbp; struct ldap *
0x180008a7d  mov     [rsp+78h+var_58], rax; unsigned __int64
0x180008a82  call    ?GetSpecifiedL0KeyLdap@@YAJPEAUldap@@PEAGPEAU_GUID@@K_KPEAPEAU_L0_key@@@Z; GetSpecifiedL0KeyLdap(ldap *,ushort *,_GUID *,ulong,unsigned __int64,_L0_key * *)
0x180008a87  mov     ebx, eax
0x180008a89  test    eax, eax
0x180008a8b  jns     short loc_180008ABE
0x180008a8d  mov     r9d, 6A5h
0x180008a93  jmp     loc_1800089DE
0x180008a98  mov     rdx, [rsp+78h+lpMem]; unsigned __int16 *
0x180008a9d  lea     r9, [rsp+78h+var_48]; struct _L0_key **
0x180008aa2  mov     r8d, r14d; unsigned int
0x180008aa5  mov     rcx, rbp; struct ldap *
0x180008aa8  call    ?GetLatestL0KeyLdap@@YAJPEAUldap@@PEAGKPEAPEAU_L0_key@@@Z; GetLatestL0KeyLdap(ldap *,ushort *,ulong,_L0_key * *)
0x180008aad  mov     ebx, eax
0x180008aaf  test    eax, eax
0x180008ab1  jns     short loc_180008ABE
0x180008ab3  mov     r9d, 691h
0x180008ab9  jmp     loc_1800089DE
0x180008abe  mov     rax, [rsp+78h+var_48]
0x180008ac3  mov     [r12], rax
0x180008ac7  mov     [rsp+78h+var_48], 0
0x180008ad0  mov     rcx, [rsp+78h+var_48]; lpMem
0x180008ad5  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x180008ada  mov     rcx, [rsp+78h+lpMem]; lpMem
0x180008adf  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180008ae4  mov     eax, ebx
0x180008ae6  add     rsp, 48h
0x180008aea  pop     r15
0x180008aec  pop     r14
0x180008aee  pop     r12
0x180008af0  pop     rdi
0x180008af1  pop     rbp
0x180008af2  pop     rbx
0x180008af3  retn
```
