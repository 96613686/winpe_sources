# CommonUtil::HrSetFileAccess(ushort const *,void *,ulong,CommonUtil::ACCESS_ACL_TYPE)

- ea: `0x180006a2c`
- end: `0x180006cdc`
- name: `?HrSetFileAccess@CommonUtil@@YAJPEBGPEAXKW4ACCESS_ACL_TYPE@1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(struct CommonUtil::ISecurityAttributes **, __int64, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800057f4`

## callees

- `0x180006898`
- `0x180006954`
- `0x180006a2c`
- `0x180007fdc`
- `0x1800081e0`
- `0x1800090e4`
- `0x18000a010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x180006bd7`
- `ADVAPI32!SetFileSecurityW` at `0x180006bd7`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrSetFileAccess(
        struct CommonUtil::ISecurityAttributes **a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int FileSecurity; // ebx
  volatile signed __int32 *v7; // r8
  volatile signed __int32 *v9; // rbx
  __int64 v10; // r12
  int LastFailure; // r14d
  volatile signed __int32 *v12; // r8
  void (__fastcall **v13)(volatile signed __int32 *, __int64); // rax
  volatile signed __int32 *v14; // rcx
  ACL *v15; // rax
  struct _ACL *v16; // r8
  void *v17; // r9
  __int64 v18; // rcx
  volatile signed __int32 *v19; // rcx
  volatile signed __int32 *v20; // [rsp+30h] [rbp-48h] BYREF
  volatile signed __int32 *v21; // [rsp+38h] [rbp-40h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+60h] [rbp-18h]

  v21 = 0;
  FileSecurity = CommonUtil::UtilGetFileSecurity((CommonUtil *)&v21, a1, a3, a4);
  if ( FileSecurity < 0 )
  {
    v7 = v21;
    if ( v21 )
    {
      if ( *((_DWORD *)v21 + 2) == 1 )
      {
        *((_DWORD *)v21 + 2) = 0;
        goto LABEL_6;
      }
      if ( _InterlockedDecrement(v21 + 2) <= 0 )
      {
LABEL_6:
        if ( v7 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v7)(v7, 1);
      }
    }
    return (unsigned int)FileSecurity;
  }
  v9 = v21;
  v20 = 0;
  v10 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 24LL))(v21);
  LastFailure = CommonUtil::HrAddSidAccessToDacl(&v20, v10, a2);
  if ( LastFailure < 0
    || (v23 = 0,
        memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor)),
        v15 = (ACL *)(*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20),
        LastFailure = CommonUtil::UtilInitializeSecurityDescriptor(pSecurityDescriptor, v15, v16, v17),
        LastFailure < 0) )
  {
    v12 = v20;
    if ( !v20 )
      goto LABEL_17;
    if ( *((_DWORD *)v20 + 2) == 1 )
    {
      *((_DWORD *)v20 + 2) = 0;
    }
    else if ( _InterlockedDecrement(v20 + 2) > 0 )
    {
      goto LABEL_17;
    }
    if ( v12 )
    {
      v13 = *(void (__fastcall ***)(volatile signed __int32 *, __int64))v12;
      v14 = v12;
LABEL_16:
      (*v13)(v14, 1);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( !SetFileSecurityW((LPCWSTR)a1, 4u, pSecurityDescriptor) )
  {
    LastFailure = HrGetLastFailure(v18);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_917185ddc84637471a8d5a2f656085a7_Traceguids,
        (_DWORD)a1,
        LastFailure);
    if ( LastFailure < 0 )
    {
      v14 = v20;
      if ( !v20 )
        goto LABEL_17;
      if ( *((_DWORD *)v20 + 2) == 1 )
      {
        *((_DWORD *)v20 + 2) = 0;
      }
      else if ( _InterlockedDecrement(v20 + 2) > 0 )
      {
        goto LABEL_17;
      }
      if ( v14 )
      {
        v13 = *(void (__fastcall ***)(volatile signed __int32 *, __int64))v14;
        goto LABEL_16;
      }
LABEL_17:
      if ( v9 )
      {
        if ( *((_DWORD *)v9 + 2) == 1 )
        {
          *((_DWORD *)v9 + 2) = 0;
LABEL_21:
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v9)(v9, 1);
          return (unsigned int)LastFailure;
        }
        if ( _InterlockedDecrement(v9 + 2) <= 0 )
          goto LABEL_21;
      }
      return (unsigned int)LastFailure;
    }
  }
  v19 = v20;
  if ( v20 )
  {
    if ( *((_DWORD *)v20 + 2) == 1 )
    {
      *((_DWORD *)v20 + 2) = 0;
    }
    else if ( _InterlockedDecrement(v20 + 2) > 0 )
    {
      goto LABEL_41;
    }
    if ( v19 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v19)(v19, 1);
  }
LABEL_41:
  if ( v9 )
  {
    if ( *((_DWORD *)v9 + 2) == 1 )
    {
      *((_DWORD *)v9 + 2) = 0;
LABEL_45:
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v9)(v9, 1);
      return 0;
    }
    if ( _InterlockedDecrement(v9 + 2) <= 0 )
      goto LABEL_45;
  }
  return 0;
}

```

## disassembly

```asm
0x180006a2c  push    rbp
0x180006a2e  push    rbx
0x180006a2f  push    rsi
0x180006a30  push    rdi
0x180006a31  push    r12
0x180006a33  push    r13
0x180006a35  push    r14
0x180006a37  push    r15
0x180006a39  mov     rbp, rsp
0x180006a3c  sub     rsp, 78h
0x180006a40  mov     r14, rdx
0x180006a43  mov     r15, rcx
0x180006a46  mov     rdx, rcx; struct CommonUtil::ISecurityAttributes **
0x180006a49  xor     r13d, r13d
0x180006a4c  lea     rcx, [rbp+var_40]; this
0x180006a50  mov     [rbp+var_40], r13
0x180006a54  call    ?UtilGetFileSecurity@CommonUtil@@YAJPEAPEAUISecurityAttributes@1@PEBGK@Z; CommonUtil::UtilGetFileSecurity(CommonUtil::ISecurityAttributes * *,ushort const *,ulong)
0x180006a59  mov     ebx, eax
0x180006a5b  test    eax, eax
0x180006a5d  jns     short loc_180006AA7
0x180006a5f  mov     r8, [rbp+var_40]
0x180006a63  test    r8, r8
0x180006a66  jz      short loc_180006AA0
0x180006a68  mov     ecx, [r8+8]
0x180006a6c  lea     edi, [r13+1]
0x180006a70  cmp     ecx, edi
0x180006a72  jnz     short loc_180006A7A
0x180006a74  mov     [r8+8], r13d
0x180006a78  jmp     short loc_180006A8B
0x180006a7a  or      esi, 0FFFFFFFFh
0x180006a7d  mov     eax, esi
0x180006a7f  lock xadd [r8+8], eax
0x180006a85  add     eax, esi
0x180006a87  test    eax, eax
0x180006a89  jg      short loc_180006AA0
0x180006a8b  test    r8, r8
0x180006a8e  jz      short loc_180006AA0
0x180006a90  mov     rax, [r8]
0x180006a93  mov     edx, edi
0x180006a95  mov     rcx, r8
0x180006a98  mov     rax, [rax]
0x180006a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa0  mov     eax, ebx
0x180006aa2  jmp     loc_180006CCB
0x180006aa7  mov     rbx, [rbp+var_40]
0x180006aab  mov     [rbp+var_48], r13
0x180006aaf  mov     rcx, rbx
0x180006ab2  mov     rax, [rbx]
0x180006ab5  mov     rax, [rax+18h]
0x180006ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006abe  mov     r8, [rbp+var_48]
0x180006ac2  or      esi, 0FFFFFFFFh
0x180006ac5  mov     r12, rax
0x180006ac8  mov     edi, 1
0x180006acd  test    r8, r8
0x180006ad0  jz      short loc_180006B07
0x180006ad2  mov     ecx, [r8+8]
0x180006ad6  cmp     ecx, edi
0x180006ad8  jnz     short loc_180006AE0
0x180006ada  mov     [r8+8], r13d
0x180006ade  jmp     short loc_180006AEE
0x180006ae0  mov     eax, esi
0x180006ae2  lock xadd [r8+8], eax
0x180006ae8  add     eax, esi
0x180006aea  test    eax, eax
0x180006aec  jg      short loc_180006B03
0x180006aee  test    r8, r8
0x180006af1  jz      short loc_180006B03
0x180006af3  mov     rax, [r8]
0x180006af6  mov     edx, edi
0x180006af8  mov     rcx, r8
0x180006afb  mov     rax, [rax]
0x180006afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b03  mov     [rbp+var_48], r13
0x180006b07  mov     r8, r14
0x180006b0a  lea     rcx, [rbp+var_48]
0x180006b0e  mov     rdx, r12
0x180006b11  call    CommonUtil__HrAddSidAccessToDacl
0x180006b16  mov     r14d, eax
0x180006b19  test    eax, eax
0x180006b1b  jns     short loc_180006B93
0x180006b1d  mov     r8, [rbp+var_48]
0x180006b21  test    r8, r8
0x180006b24  jz      short loc_180006B57
0x180006b26  mov     ecx, [r8+8]
0x180006b2a  cmp     ecx, edi
0x180006b2c  jnz     short loc_180006B34
0x180006b2e  mov     [r8+8], r13d
0x180006b32  jmp     short loc_180006B42
0x180006b34  mov     eax, esi
0x180006b36  lock xadd [r8+8], eax
0x180006b3c  add     eax, esi
0x180006b3e  test    eax, eax
0x180006b40  jg      short loc_180006B57
0x180006b42  test    r8, r8
0x180006b45  jz      short loc_180006B57
0x180006b47  mov     rax, [r8]
0x180006b4a  mov     rcx, r8
0x180006b4d  mov     rax, [rax]
0x180006b50  mov     edx, edi
0x180006b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b57  test    rbx, rbx
0x180006b5a  jz      short loc_180006B8B
0x180006b5c  mov     eax, [rbx+8]
0x180006b5f  cmp     eax, edi
0x180006b61  jnz     short loc_180006B69
0x180006b63  mov     [rbx+8], r13d
0x180006b67  jmp     short loc_180006B76
0x180006b69  mov     eax, esi
0x180006b6b  lock xadd [rbx+8], eax
0x180006b70  add     eax, esi
0x180006b72  test    eax, eax
0x180006b74  jg      short loc_180006B8B
0x180006b76  test    rbx, rbx
0x180006b79  jz      short loc_180006B8B
0x180006b7b  mov     rax, [rbx]
0x180006b7e  mov     edx, edi
0x180006b80  mov     rcx, rbx
0x180006b83  mov     rax, [rax]
0x180006b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b8b  mov     eax, r14d
0x180006b8e  jmp     loc_180006CCB
0x180006b93  mov     rcx, [rbp+var_48]
0x180006b97  xor     eax, eax
0x180006b99  xorps   xmm0, xmm0
0x180006b9c  mov     [rbp+var_18], rax
0x180006ba0  movups  [rbp+pSecurityDescriptor], xmm0
0x180006ba4  movups  [rbp+var_28], xmm0
0x180006ba8  mov     rax, [rcx]
0x180006bab  mov     rax, [rax+8]
0x180006baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb4  mov     rdx, rax; pDacl
0x180006bb7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180006bbb  call    ?UtilInitializeSecurityDescriptor@CommonUtil@@YAJPEAXPEAU_ACL@@0@Z; CommonUtil::UtilInitializeSecurityDescriptor(void *,_ACL *,void *)
0x180006bc0  mov     r14d, eax
0x180006bc3  test    eax, eax
0x180006bc5  js      loc_180006B1D
0x180006bcb  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180006bcf  mov     edx, 4; SecurityInformation
0x180006bd4  mov     rcx, r15; lpFileName
0x180006bd7  call    cs:__imp_SetFileSecurityW
0x180006bdd  test    eax, eax
0x180006bdf  jnz     short loc_180006C60
0x180006be1  call    HrGetLastFailure
0x180006be6  mov     r14d, eax
0x180006be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bf0  lea     rax, WPP_GLOBAL_Control
0x180006bf7  cmp     rcx, rax
0x180006bfa  jz      short loc_180006C1F
0x180006bfc  test    [rcx+1Ch], dil
0x180006c00  jz      short loc_180006C1F
0x180006c02  mov     rcx, [rcx+10h]
0x180006c06  lea     r8, WPP_917185ddc84637471a8d5a2f656085a7_Traceguids
0x180006c0d  mov     edx, 17h
0x180006c12  mov     [rsp+78h+var_58], r14d
0x180006c17  mov     r9, r15
0x180006c1a  call    WPP_SF_Sd
0x180006c1f  test    r14d, r14d
0x180006c22  jns     short loc_180006C60
0x180006c24  mov     rcx, [rbp+var_48]
0x180006c28  test    rcx, rcx
0x180006c2b  jz      loc_180006B57
0x180006c31  mov     eax, [rcx+8]
0x180006c34  cmp     eax, edi
0x180006c36  jnz     short loc_180006C3E
0x180006c38  mov     [rcx+8], r13d
0x180006c3c  jmp     short loc_180006C4F
0x180006c3e  mov     eax, esi
0x180006c40  lock xadd [rcx+8], eax
0x180006c45  add     eax, esi
0x180006c47  test    eax, eax
0x180006c49  jg      loc_180006B57
0x180006c4f  test    rcx, rcx
0x180006c52  jz      loc_180006B57
0x180006c58  mov     rax, [rcx]
0x180006c5b  jmp     loc_180006B4D
0x180006c60  mov     rcx, [rbp+var_48]
0x180006c64  test    rcx, rcx
0x180006c67  jz      short loc_180006C95
0x180006c69  mov     eax, [rcx+8]
0x180006c6c  cmp     eax, edi
0x180006c6e  jnz     short loc_180006C76
0x180006c70  mov     [rcx+8], r13d
0x180006c74  jmp     short loc_180006C83
0x180006c76  mov     eax, esi
0x180006c78  lock xadd [rcx+8], eax
0x180006c7d  add     eax, esi
0x180006c7f  test    eax, eax
0x180006c81  jg      short loc_180006C95
0x180006c83  test    rcx, rcx
0x180006c86  jz      short loc_180006C95
0x180006c88  mov     rax, [rcx]
0x180006c8b  mov     edx, edi
0x180006c8d  mov     rax, [rax]
0x180006c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c95  test    rbx, rbx
0x180006c98  jz      short loc_180006CC9
0x180006c9a  mov     eax, [rbx+8]
0x180006c9d  cmp     eax, edi
0x180006c9f  jnz     short loc_180006CA7
0x180006ca1  mov     [rbx+8], r13d
0x180006ca5  jmp     short loc_180006CB4
0x180006ca7  mov     eax, esi
0x180006ca9  lock xadd [rbx+8], eax
0x180006cae  add     eax, esi
0x180006cb0  test    eax, eax
0x180006cb2  jg      short loc_180006CC9
0x180006cb4  test    rbx, rbx
0x180006cb7  jz      short loc_180006CC9
0x180006cb9  mov     rax, [rbx]
0x180006cbc  mov     edx, edi
0x180006cbe  mov     rcx, rbx
0x180006cc1  mov     rax, [rax]
0x180006cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc9  xor     eax, eax
0x180006ccb  add     rsp, 78h
0x180006ccf  pop     r15
0x180006cd1  pop     r14
0x180006cd3  pop     r13
0x180006cd5  pop     r12
0x180006cd7  pop     rdi
0x180006cd8  pop     rsi
0x180006cd9  pop     rbx
0x180006cda  pop     rbp
0x180006cdb  retn
```
