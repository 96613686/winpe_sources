# HandleGetUnlockKey(ICloudAPContext *,void *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS *,eUnlockKeyType *,_AP_BLOB *)

- ea: `0x1800144b4`
- end: `0x1800146de`
- name: `?HandleGetUnlockKey@@YAJPEAVICloudAPContext@@PEAXPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAW4eUnlockKeyType@@PEAU_AP_BLOB@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *, enum eUnlockKeyType *, struct _AP_BLOB *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180009e70`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d968`
- `0x18000ed44`
- `0x1800144b4`
- `0x1800267c0`

## string_xrefs

- `0x180014518`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800145b8`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014632`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x18001469c`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HandleGetUnlockKey(
        struct ICloudAPContext *a1,
        void *a2,
        struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *a3,
        enum eUnlockKeyType *a4,
        struct _AP_BLOB *a5)
{
  struct _AP_BLOB *v8; // rbx
  struct LOGON_CREDS *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // ecx
  __int64 v13; // rax
  unsigned int v14; // ebx
  const unsigned __int16 *v16; // [rsp+20h] [rbp-41h]
  const unsigned __int16 *v17; // [rsp+20h] [rbp-41h]
  struct LOGON_CREDS *v18[3]; // [rsp+30h] [rbp-31h] BYREF
  __int128 v19; // [rsp+48h] [rbp-19h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v20; // [rsp+58h] [rbp-9h]
  _QWORD v21[10]; // [rsp+60h] [rbp-1h] BYREF
  int LogonCredsFromAuthData; // [rsp+C8h] [rbp+67h] BYREF
  int v23; // [rsp+CCh] [rbp+6Bh]

  v23 = HIDWORD(a2);
  LogonCredsFromAuthData = 0;
  v19 = 0;
  v20 = 0;
  memset(v18, 0, sizeof(v18));
  v21[0] = "HandleGetUnlockKey";
  v21[1] = &LogonCredsFromAuthData;
  v21[2] = 0;
  v21[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleGetUnlockKey",
    (const char *)0x1C,
    0,
    v16);
  if ( !a3 || !a4 || (v8 = a5) == 0 )
  {
    LogonCredsFromAuthData = -1073741811;
    goto LABEL_21;
  }
  *(_DWORD *)a4 = 0;
  *(_QWORD *)v8 = 0;
  *((_QWORD *)v8 + 1) = 0;
  v20 = a3;
  LogonCredsFromAuthData = GetLogonCredsFromAuthData(a1, (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **)&v19, v18);
  if ( LogonCredsFromAuthData >= 0 )
  {
    v9 = v18[0];
    if ( (*((_DWORD *)v18[0] + 52) & 0x200) != 0 )
    {
      *(_QWORD *)v8 = 0;
      *((_QWORD *)v8 + 1) = 0;
      *(_DWORD *)a4 = 1;
      LogonCredsFromAuthData = 0;
    }
    else
    {
      if ( *((_DWORD *)v18[0] + 6) != 1 )
      {
        if ( *((_DWORD *)v18[0] + 6) != 3 )
        {
          LogonCredsFromAuthData = -1073741811;
          LODWORD(v17) = *((_DWORD *)v18[0] + 6);
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
            0x55u,
            L"Invalid credType = %lu, Status=0x%x.",
            v17,
            -1073741811);
          goto LABEL_21;
        }
        if ( !*((_QWORD *)v18[0] + 16) )
        {
          LogonCredsFromAuthData = -1073741811;
          LODWORD(v17) = -1073741811;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
            0x4Bu,
            L"sessionkeyValue == nullptr. Status=0x%x.",
            v17);
          if ( LogonCredsFromAuthData < 0 )
            goto LABEL_21;
          v9 = v18[0];
        }
        v12 = *((_DWORD *)v9 + 44);
        v13 = *((_QWORD *)v9 + 16);
        *((_QWORD *)v9 + 16) = 0;
        *((_QWORD *)v9 + 17) = 0;
        *(_QWORD *)v8 = v12;
        *((_QWORD *)v8 + 1) = v13;
        *(_DWORD *)a4 = 5;
        goto LABEL_21;
      }
      if ( !*((_QWORD *)v18[0] + 4) )
      {
        LogonCredsFromAuthData = -1073741811;
        LODWORD(v17) = -1073741811;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x3Fu,
          L"credValue == nullptr. Status=0x%x.",
          v17);
        if ( LogonCredsFromAuthData < 0 )
          goto LABEL_21;
        v9 = v18[0];
      }
      v10 = *((_QWORD *)v9 + 4);
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      *((_QWORD *)v9 + 4) = 0;
      *((_QWORD *)v9 + 5) = 0;
      *(_QWORD *)v8 = (unsigned int)(2 * v11);
      *((_QWORD *)v8 + 1) = v10;
      *(_DWORD *)a4 = 1;
    }
  }
LABEL_21:
  v14 = LogonCredsFromAuthData;
  CTraceFuncW<long>::~CTraceFuncW<long>(v21);
  Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::~Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>(v18);
  return v14;
}

```

## disassembly

```asm
0x1800144b4  mov     [rsp-8+arg_8], rdx
0x1800144b9  push    rbp
0x1800144ba  push    rbx
0x1800144bb  push    rsi
0x1800144bc  push    rdi
0x1800144bd  push    r14
0x1800144bf  push    r15
0x1800144c1  lea     rbp, [rsp-27h]
0x1800144c6  sub     rsp, 88h
0x1800144cd  mov     rdi, r9
0x1800144d0  mov     rsi, r8
0x1800144d3  mov     r14, rcx
0x1800144d6  xor     r15d, r15d
0x1800144d9  mov     dword ptr [rbp+4Fh+arg_8], r15d
0x1800144dd  xorps   xmm0, xmm0
0x1800144e0  xor     eax, eax
0x1800144e2  movups  [rbp+4Fh+var_68], xmm0
0x1800144e6  mov     [rbp+4Fh+var_58], rax
0x1800144ea  mov     [rbp+4Fh+var_80], r15
0x1800144ee  mov     [rbp+4Fh+var_70], r15
0x1800144f2  mov     [rbp+4Fh+var_78], r15
0x1800144f6  lea     rdx, aHandlegetunloc; "HandleGetUnlockKey"
0x1800144fd  mov     [rbp+4Fh+var_50], rdx
0x180014501  lea     rax, [rbp+4Fh+arg_8]
0x180014505  mov     [rbp+4Fh+var_48], rax
0x180014509  mov     [rbp+4Fh+var_40], r15
0x18001450d  mov     [rbp+4Fh+var_38], r15
0x180014511  xor     r9d, r9d; unsigned int
0x180014514  lea     r8d, [r15+1Ch]; char *
0x180014518  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18001451f  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180014524  nop
0x180014525  test    rsi, rsi
0x180014528  jz      loc_1800146AE
0x18001452e  test    rdi, rdi
0x180014531  jz      loc_1800146AE
0x180014537  mov     rbx, [rbp+4Fh+arg_20]
0x18001453b  test    rbx, rbx
0x18001453e  jz      loc_1800146AE
0x180014544  mov     [rdi], r15d
0x180014547  mov     [rbx], r15
0x18001454a  mov     [rbx+8], r15
0x18001454e  mov     [rbp+4Fh+var_58], rsi
0x180014552  lea     r8, [rbp+4Fh+var_80]; struct LOGON_CREDS **
0x180014556  lea     rdx, [rbp+4Fh+var_68]; struct _DECRYPTED_AUTH_DATA *
0x18001455a  mov     rcx, r14; struct ICloudAPContext *
0x18001455d  call    ?GetLogonCredsFromAuthData@@YAJPEAVICloudAPContext@@PEAU_DECRYPTED_AUTH_DATA@@PEAPEAULOGON_CREDS@@@Z; GetLogonCredsFromAuthData(ICloudAPContext *,_DECRYPTED_AUTH_DATA *,LOGON_CREDS * *)
0x180014562  mov     dword ptr [rbp+4Fh+arg_8], eax
0x180014565  test    eax, eax
0x180014567  js      loc_1800146B6
0x18001456d  mov     rdx, [rbp+4Fh+var_80]
0x180014571  test    dword ptr [rdx+0D0h], 200h
0x18001457b  jz      short loc_180014593
0x18001457d  mov     [rbx], r15
0x180014580  mov     [rbx+8], r15
0x180014584  mov     dword ptr [rdi], 1
0x18001458a  mov     dword ptr [rbp+4Fh+arg_8], r15d
0x18001458e  jmp     loc_1800146B6
0x180014593  cmp     dword ptr [rdx+18h], 1
0x180014597  jnz     short loc_18001460A
0x180014599  cmp     [rdx+20h], r15
0x18001459d  jnz     short loc_1800145D6
0x18001459f  mov     eax, 0C000000Dh
0x1800145a4  mov     dword ptr [rbp+4Fh+arg_8], eax
0x1800145a7  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800145ab  lea     r9, aCredvalueNullp; "credValue == nullptr. Status=0x%x."
0x1800145b2  mov     r8d, 3Fh ; '?'; unsigned int
0x1800145b8  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800145bf  lea     ecx, [r8-3Dh]; unsigned __int8
0x1800145c3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800145c8  cmp     dword ptr [rbp+4Fh+arg_8], r15d
0x1800145cc  jl      loc_1800146B6
0x1800145d2  mov     rdx, [rbp+4Fh+var_80]
0x1800145d6  mov     rcx, [rdx+20h]
0x1800145da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800145de  inc     rax
0x1800145e1  cmp     [rcx+rax*2], r15w
0x1800145e6  jnz     short loc_1800145DE
0x1800145e8  add     eax, eax
0x1800145ea  xor     r8d, r8d
0x1800145ed  mov     [rdx+20h], r15
0x1800145f1  mov     [rdx+28h], r15
0x1800145f5  mov     [rbx], eax
0x1800145f7  mov     [rbx+4], r8d
0x1800145fb  mov     [rbx+8], rcx
0x1800145ff  mov     dword ptr [rdi], 1
0x180014605  jmp     loc_1800146B6
0x18001460a  cmp     dword ptr [rdx+18h], 3
0x18001460e  jnz     short loc_18001467C
0x180014610  cmp     [rdx+80h], r15
0x180014617  jnz     short loc_18001464C
0x180014619  mov     eax, 0C000000Dh
0x18001461e  mov     dword ptr [rbp+4Fh+arg_8], eax
0x180014621  mov     dword ptr [rsp+0B0h+var_90], eax
0x180014625  lea     r9, aSessionkeyvalu; "sessionkeyValue == nullptr. Status=0x%x"...
0x18001462c  mov     r8d, 4Bh ; 'K'; unsigned int
0x180014632  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014639  lea     ecx, [r8-49h]; unsigned __int8
0x18001463d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014642  cmp     dword ptr [rbp+4Fh+arg_8], r15d
0x180014646  jl      short loc_1800146B6
0x180014648  mov     rdx, [rbp+4Fh+var_80]
0x18001464c  mov     ecx, [rdx+0B0h]
0x180014652  xor     r8d, r8d
0x180014655  mov     rax, [rdx+80h]
0x18001465c  mov     [rdx+80h], r15
0x180014663  mov     [rdx+88h], r15
0x18001466a  mov     [rbx], ecx
0x18001466c  mov     [rbx+4], r8d
0x180014670  mov     [rbx+8], rax
0x180014674  mov     dword ptr [rdi], 5
0x18001467a  jmp     short loc_1800146B6
0x18001467c  mov     eax, 0C000000Dh
0x180014681  mov     dword ptr [rbp+4Fh+arg_8], eax
0x180014684  mov     [rsp+0B0h+var_88], eax
0x180014688  mov     eax, [rdx+18h]
0x18001468b  mov     dword ptr [rsp+0B0h+var_90], eax
0x18001468f  lea     r9, aInvalidCredtyp; "Invalid credType = %lu, Status=0x%x."
0x180014696  mov     r8d, 55h ; 'U'; unsigned int
0x18001469c  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800146a3  lea     ecx, [r8-53h]; unsigned __int8
0x1800146a7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800146ac  jmp     short loc_1800146B6
0x1800146ae  mov     eax, 0C000000Dh
0x1800146b3  mov     dword ptr [rbp+4Fh+arg_8], eax
0x1800146b6  mov     ebx, dword ptr [rbp+4Fh+arg_8]
0x1800146b9  lea     rcx, [rbp+4Fh+var_50]
0x1800146bd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800146c2  nop
0x1800146c3  lea     rcx, [rbp+4Fh+var_80]
0x1800146c7  call    ??1?$Auto@PEAULOGON_CREDS@@VLogonCredsFunctor@@VDummyContext@@@@QEAA@XZ; Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::~Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>(void)
0x1800146cc  mov     eax, ebx
0x1800146ce  add     rsp, 88h
0x1800146d5  pop     r15
0x1800146d7  pop     r14
0x1800146d9  pop     rdi
0x1800146da  pop     rsi
0x1800146db  pop     rbx
0x1800146dc  pop     rbp
0x1800146dd  retn
```
