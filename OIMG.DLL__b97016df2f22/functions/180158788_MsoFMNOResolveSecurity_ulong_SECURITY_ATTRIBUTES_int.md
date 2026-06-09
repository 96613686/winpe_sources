# MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)

- ea: `0x180158788`
- end: `0x180158afe`
- name: `?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `886`
- prototype: `int(unsigned int, struct _SECURITY_ATTRIBUTES **, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801438a0`
- `0x180157418`
- `0x180157568`
- `0x1801576c4`

## callees

- `0x18001373c`
- `0x1801579f4`
- `0x180157c48`
- `0x180157fb0`
- `0x1801580a0`
- `0x180158228`
- `0x180158448`
- `0x1801585ec`
- `0x1801586e0`
- `0x180158788`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180158a0d`
- `KERNEL32!LocalFree` at `0x180158a1b`
- `KERNEL32!LocalFree` at `0x180158a29`
- `KERNEL32!LocalFree` at `0x180158a0d`
- `KERNEL32!LocalFree` at `0x180158a1b`
- `KERNEL32!LocalFree` at `0x180158a29`
- `KERNEL32!GlobalFree` at `0x180158986`
- `KERNEL32!GlobalFree` at `0x180158986`
- `KERNEL32!LocalAlloc` at `0x1801588f9`
- `KERNEL32!LocalAlloc` at `0x1801589a5`
- `KERNEL32!LocalAlloc` at `0x180158a9c`
- `KERNEL32!LocalAlloc` at `0x1801588f9`
- `KERNEL32!LocalAlloc` at `0x1801589a5`
- `KERNEL32!LocalAlloc` at `0x180158a9c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1801589d4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1801589d4`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1801589be`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1801589be`

## pseudocode

```c
__int64 __fastcall MsoFMNOResolveSecurity(int a1, struct _SECURITY_ATTRIBUTES **a2, __int64 a3, int a4)
{
  unsigned __int8 v6; // di
  __int64 v8; // rbp
  struct _SECURITY_ATTRIBUTES * near **v9; // rdi
  struct _SECURITY_ATTRIBUTES * near *v10; // rax
  __int64 v11; // rbp
  __int64 v12; // rbp
  __int64 v13; // rbp
  __int64 v14; // rbp
  ACL *v15; // rbp
  void *v16; // r14
  int v17; // r13d
  struct _SECURITY_ATTRIBUTES *v18; // rax
  struct _SECURITY_ATTRIBUTES *v19; // rdi
  bool v20; // r15
  BOOL v21; // eax
  __int64 v22; // rdx
  const unsigned int *v23; // rcx
  __int64 v24; // r9
  HGLOBAL v25; // r12
  ACL *v26; // r13
  HLOCAL v27; // rax
  char v28; // al
  unsigned int *v29; // rax
  int v30; // ebx
  struct _SECURITY_ATTRIBUTES *v31; // rax
  struct _SECURITY_ATTRIBUTES *v32; // rbx
  void *v33; // [rsp+30h] [rbp-48h] BYREF
  char v34; // [rsp+88h] [rbp+10h]
  HGLOBAL hMem; // [rsp+98h] [rbp+20h] BYREF

  v6 = 1;
  if ( !a2 )
    return 0;
  if ( (a1 & 0x2000) != 0 )
  {
    v8 = (int)a3;
    v9 = &vrgpsaEveryone;
    if ( (a1 & 0x40000) != 0 )
    {
      if ( !(&vrgpsaEveryoneAA)[(int)a3] )
        sub_1801580A0((unsigned int)a3);
    }
    else if ( !(&vrgpsaEveryone)[(int)a3] )
    {
      sub_180157FB0((unsigned int)a3);
    }
    if ( (a1 & 0x40000) != 0 )
      v9 = &vrgpsaEveryoneAA;
    v10 = v9[v8];
  }
  else if ( (a1 & 0x4000) != 0 )
  {
    v11 = (int)a3;
    if ( !(&vrgpsaLogonId)[(int)a3] )
      FCreateLogonIdDaclSa((unsigned int *)(unsigned int)a3, (int)a2, a3, a4);
    v10 = (&vrgpsaLogonId)[v11];
  }
  else if ( (a1 & 0x8000) != 0 )
  {
    v12 = (int)a3;
    if ( !(&vrgpsaUser)[(int)a3] )
      FCreateUserDaclSa(a3);
    v10 = (&vrgpsaUser)[v12];
  }
  else if ( (a1 & 0x10000) != 0 )
  {
    v13 = (int)a3;
    if ( !(&vrgpsaInteractiveUser)[(int)a3] )
      sub_1801585EC((unsigned int)a3);
    v10 = (&vrgpsaInteractiveUser)[v13];
  }
  else
  {
    if ( (a1 & 0x20000) == 0 )
    {
      if ( (a1 & 0x100000) != 0 )
      {
        v34 = 0;
        v15 = 0;
        v16 = 0;
        v17 = dword_1805D5CF0[(int)a3];
        v18 = (struct _SECURITY_ATTRIBUTES *)LocalAlloc(0x40u, 0x18u);
        *a2 = v18;
        v19 = v18;
        if ( v18 )
        {
          v20 = 0;
          hMem = 0;
          v21 = FAllocateAndRetrieveUserSid(2, &hMem);
          v25 = hMem;
          if ( v21 )
          {
            v33 = hMem;
            LODWORD(hMem) = v17 & 0xEEE0FFFF | 0x120000;
            v26 = MsoCreateAcl(v23, v22, (DWORD *)&hMem, v24, &v33);
            v20 = v26 != 0;
          }
          else
          {
            v26 = 0;
          }
          if ( v25 )
            GlobalFree(v25);
          if ( v20
            && (v15 = v26) != 0
            && (v27 = LocalAlloc(0x40u, 0x28u), (v16 = v27) != 0)
            && InitializeSecurityDescriptor(v27, 1u)
            && SetSecurityDescriptorDacl(v16, 1, v26, 0) )
          {
            v28 = 1;
            v19->nLength = 24;
            v34 = 1;
            v19->lpSecurityDescriptor = v16;
            v19->bInheritHandle = 0;
          }
          else
          {
            v28 = 0;
          }
        }
        else
        {
          v28 = 0;
        }
        if ( !v28 )
        {
          if ( v15 )
            LocalFree(v15);
          if ( v16 )
            LocalFree(v16);
          if ( v19 )
            LocalFree(v19);
          *a2 = 0;
        }
        v6 = v34;
      }
      else if ( (a1 & 0x80000) == 0 )
      {
        MsoShipAssertTagProc(1422217);
      }
      goto LABEL_55;
    }
    v14 = (int)a3;
    if ( !(&vrgpsaAdministrators)[(int)a3] )
      sub_1801586E0((unsigned int)a3);
    v10 = (&vrgpsaAdministrators)[v14];
  }
  *a2 = (struct _SECURITY_ATTRIBUTES *)v10;
  v6 = 1;
LABEL_55:
  v29 = (unsigned int *)*a2;
  if ( *a2 && (a1 & 0x800000) != 0 )
  {
    v30 = a1 & 0x1FE000;
    if ( v30 == 0x2000 || v30 == 0x4000 || v30 == 0x8000 || v30 == 0x10000 || v30 == 0x20000 )
    {
      v31 = (struct _SECURITY_ATTRIBUTES *)LocalAlloc(0x40u, *v29);
      v32 = v31;
      if ( v31 )
      {
        v31->nLength = (*a2)->nLength;
        v31->lpSecurityDescriptor = (*a2)->lpSecurityDescriptor;
        v31->bInheritHandle = 1;
      }
      else
      {
        MsoShipAssertTagProc(1422219);
        v6 = 0;
      }
      *a2 = v32;
    }
    else if ( v30 == 0x100000 )
    {
      v29[4] = 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180158788  mov     [rsp+arg_0], rbx
0x18015878d  push    rbp
0x18015878e  push    rsi
0x18015878f  push    rdi
0x180158790  push    r12
0x180158792  push    r13
0x180158794  push    r14
0x180158796  push    r15
0x180158798  sub     rsp, 40h
0x18015879c  xor     r12d, r12d
0x18015879f  mov     r15d, 1
0x1801587a5  mov     rsi, rdx
0x1801587a8  mov     ebx, ecx
0x1801587aa  mov     dil, r15b
0x1801587ad  test    rdx, rdx
0x1801587b0  jnz     short loc_1801587B9
0x1801587b2  xor     eax, eax
0x1801587b4  jmp     loc_180158AC7
0x1801587b9  bt      ebx, 0Dh
0x1801587bd  jnb     short loc_18015880B
0x1801587bf  mov     r14d, ebx
0x1801587c2  movsxd  rbp, r8d
0x1801587c5  lea     rdi, ?vrgpsaEveryone@@3PAPEAU_SECURITY_ATTRIBUTES@@A; _SECURITY_ATTRIBUTES * near * vrgpsaEveryone
0x1801587cc  lea     r13, ?vrgpsaEveryoneAA@@3PAPEAU_SECURITY_ATTRIBUTES@@A; _SECURITY_ATTRIBUTES * near * vrgpsaEveryoneAA
0x1801587d3  and     r14d, 40000h
0x1801587da  jnz     short loc_1801587EC
0x1801587dc  cmp     [rdi+rbp*8], r12
0x1801587e0  jnz     short loc_1801587FB
0x1801587e2  mov     ecx, r8d
0x1801587e5  call    sub_180157FB0
0x1801587ea  jmp     short loc_1801587FB
0x1801587ec  cmp     [r13+rbp*8+0], r12
0x1801587f1  jnz     short loc_1801587FB
0x1801587f3  mov     ecx, r8d
0x1801587f6  call    sub_1801580A0
0x1801587fb  test    r14d, r14d
0x1801587fe  cmovnz  rdi, r13
0x180158802  mov     rax, [rdi+rbp*8]
0x180158806  jmp     loc_1801588BC
0x18015880b  bt      ebx, 0Eh
0x18015880f  jnb     short loc_18015883A
0x180158811  movsxd  rbp, r8d
0x180158814  lea     rdi, __NULL_IMPORT_DESCRIPTOR
0x18015881b  cmp     rva ?vrgpsaLogonId@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8], r12; _SECURITY_ATTRIBUTES * near * vrgpsaLogonId ...
0x180158823  jnz     short loc_18015882D
0x180158825  mov     ecx, r8d; int
0x180158828  call    ?FCreateLogonIdDaclSa@@YA_NH@Z; FCreateLogonIdDaclSa(int)
0x18015882d  mov     rax, rva ?vrgpsaLogonId@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8]; _SECURITY_ATTRIBUTES * near * vrgpsaLogonId ...
0x180158835  jmp     loc_1801588BC
0x18015883a  bt      ebx, 0Fh
0x18015883e  jnb     short loc_180158866
0x180158840  movsxd  rbp, r8d
0x180158843  lea     rdi, __NULL_IMPORT_DESCRIPTOR
0x18015884a  cmp     rva ?vrgpsaUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8], r12; _SECURITY_ATTRIBUTES * near * vrgpsaUser ...
0x180158852  jnz     short loc_18015885C
0x180158854  mov     ecx, r8d; int
0x180158857  call    ?FCreateUserDaclSa@@YA_NH@Z; FCreateUserDaclSa(int)
0x18015885c  mov     rax, rva ?vrgpsaUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8]; _SECURITY_ATTRIBUTES * near * vrgpsaUser ...
0x180158864  jmp     short loc_1801588BC
0x180158866  bt      ebx, 10h
0x18015886a  jnb     short loc_180158892
0x18015886c  movsxd  rbp, r8d
0x18015886f  lea     rdi, __NULL_IMPORT_DESCRIPTOR
0x180158876  cmp     rva ?vrgpsaInteractiveUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8], r12; _SECURITY_ATTRIBUTES * near * vrgpsaInteractiveUser ...
0x18015887e  jnz     short loc_180158888
0x180158880  mov     ecx, r8d
0x180158883  call    sub_1801585EC
0x180158888  mov     rax, rva ?vrgpsaInteractiveUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8]; _SECURITY_ATTRIBUTES * near * vrgpsaInteractiveUser ...
0x180158890  jmp     short loc_1801588BC
0x180158892  bt      ebx, 11h
0x180158896  jnb     short loc_1801588C7
0x180158898  movsxd  rbp, r8d
0x18015889b  lea     rdi, __NULL_IMPORT_DESCRIPTOR
0x1801588a2  cmp     rva ?vrgpsaAdministrators@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8], r12; _SECURITY_ATTRIBUTES * near * vrgpsaAdministrators ...
0x1801588aa  jnz     short loc_1801588B4
0x1801588ac  mov     ecx, r8d
0x1801588af  call    sub_1801586E0
0x1801588b4  mov     rax, rva ?vrgpsaAdministrators@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rdi+rbp*8]; _SECURITY_ATTRIBUTES * near * vrgpsaAdministrators ...
0x1801588bc  mov     [rsi], rax
0x1801588bf  mov     dil, r15b
0x1801588c2  jmp     loc_180158A4B
0x1801588c7  bt      ebx, 14h
0x1801588cb  jnb     loc_180158A41
0x1801588d1  mov     edx, 18h; uBytes
0x1801588d6  movsxd  rax, r8d
0x1801588d9  lea     rdi, __NULL_IMPORT_DESCRIPTOR
0x1801588e0  mov     [rsp+78h+arg_8], r12b
0x1801588e8  mov     rbp, r12
0x1801588eb  mov     r14, r12
0x1801588ee  mov     r13d, ds:rva dword_1805D5CF0[rdi+rax*4]
0x1801588f6  lea     ecx, [rdx+28h]; uFlags
0x1801588f9  call    cs:__imp_LocalAlloc
0x1801588ff  mov     [rsi], rax
0x180158902  mov     rdi, rax
0x180158905  test    rax, rax
0x180158908  jz      loc_180158A3C
0x18015890e  lea     rdx, [rsp+78h+hMem]; void **
0x180158916  movzx   r15d, r12b
0x18015891a  mov     ecx, 2; unsigned int
0x18015891f  mov     [rsp+78h+hMem], r12
0x180158927  call    ?FAllocateAndRetrieveUserSid@@YAHKPEAPEAX@Z; FAllocateAndRetrieveUserSid(ulong,void * *)
0x18015892c  mov     r12, [rsp+78h+hMem]
0x180158934  test    eax, eax
0x180158936  jz      short loc_18015897B
0x180158938  lea     rax, [rsp+78h+var_48]
0x18015893d  mov     [rsp+78h+var_48], r12
0x180158942  and     r13d, 0EEF2FFFFh
0x180158949  mov     [rsp+78h+var_58], rax; void **
0x18015894e  or      r13d, 120000h
0x180158955  lea     r8, [rsp+78h+hMem]; unsigned int *
0x18015895d  mov     dword ptr [rsp+78h+hMem], r13d
0x180158965  call    ?MsoCreateAcl@@YAPEAU_ACL@@QEBKH0HQEAPEAX@Z; MsoCreateAcl(ulong const * const,int,ulong const * const,int,void * * const)
0x18015896a  test    rax, rax
0x18015896d  mov     r13, rax
0x180158970  mov     eax, 1
0x180158975  cmovnz  r15d, eax
0x180158979  jmp     short loc_18015897E
0x18015897b  mov     r13, rbp
0x18015897e  test    r12, r12
0x180158981  jz      short loc_18015898C
0x180158983  mov     rcx, r12; hMem
0x180158986  call    cs:__imp_GlobalFree
0x18015898c  xor     r12d, r12d
0x18015898f  test    r15b, r15b
0x180158992  cmovnz  rbp, r13
0x180158996  jz      short loc_1801589F8
0x180158998  test    rbp, rbp
0x18015899b  jz      short loc_1801589F8
0x18015899d  lea     edx, [r12+28h]; uBytes
0x1801589a2  lea     ecx, [rdx+18h]; uFlags
0x1801589a5  call    cs:__imp_LocalAlloc
0x1801589ab  lea     r15d, [r12+1]
0x1801589b0  mov     r14, rax
0x1801589b3  test    rax, rax
0x1801589b6  jz      short loc_1801589FE
0x1801589b8  mov     edx, r15d; dwRevision
0x1801589bb  mov     rcx, rax; pSecurityDescriptor
0x1801589be  call    cs:__imp_InitializeSecurityDescriptor
0x1801589c4  test    eax, eax
0x1801589c6  jz      short loc_1801589FE
0x1801589c8  xor     r9d, r9d; bDaclDefaulted
0x1801589cb  mov     r8, rbp; pDacl
0x1801589ce  mov     edx, r15d; bDaclPresent
0x1801589d1  mov     rcx, r14; pSecurityDescriptor
0x1801589d4  call    cs:__imp_SetSecurityDescriptorDacl
0x1801589da  test    eax, eax
0x1801589dc  jz      short loc_1801589FE
0x1801589de  mov     al, r15b
0x1801589e1  mov     dword ptr [rdi], 18h
0x1801589e7  mov     [rsp+78h+arg_8], al
0x1801589ee  mov     [rdi+8], r14
0x1801589f2  mov     [rdi+10h], r12d
0x1801589f6  jmp     short loc_180158A01
0x1801589f8  mov     r15d, 1
0x1801589fe  mov     al, r12b
0x180158a01  test    al, al
0x180158a03  jnz     short loc_180158A32
0x180158a05  test    rbp, rbp
0x180158a08  jz      short loc_180158A13
0x180158a0a  mov     rcx, rbp; hMem
0x180158a0d  call    cs:__imp_LocalFree
0x180158a13  test    r14, r14
0x180158a16  jz      short loc_180158A21
0x180158a18  mov     rcx, r14; hMem
0x180158a1b  call    cs:__imp_LocalFree
0x180158a21  test    rdi, rdi
0x180158a24  jz      short loc_180158A2F
0x180158a26  mov     rcx, rdi; hMem
0x180158a29  call    cs:__imp_LocalFree
0x180158a2f  mov     [rsi], r12
0x180158a32  mov     dil, [rsp+78h+arg_8]
0x180158a3a  jmp     short loc_180158A4B
0x180158a3c  mov     al, bpl
0x180158a3f  jmp     short loc_180158A01
0x180158a41  bt      ebx, 13h
0x180158a45  jnb     loc_180158AEE
0x180158a4b  mov     rax, [rsi]
0x180158a4e  test    rax, rax
0x180158a51  jz      short loc_180158AC3
0x180158a53  bt      ebx, 17h
0x180158a57  jnb     short loc_180158AC3
0x180158a59  and     ebx, 1FE000h
0x180158a5f  cmp     ebx, 2000h
0x180158a65  jz      short loc_180158A95
0x180158a67  cmp     ebx, 4000h
0x180158a6d  jz      short loc_180158A95
0x180158a6f  cmp     ebx, 8000h
0x180158a75  jz      short loc_180158A95
0x180158a77  cmp     ebx, 10000h
0x180158a7d  jz      short loc_180158A95
0x180158a7f  cmp     ebx, 20000h
0x180158a85  jz      short loc_180158A95
0x180158a87  cmp     ebx, 100000h
0x180158a8d  jnz     short loc_180158AC3
0x180158a8f  mov     [rax+10h], r15d
0x180158a93  jmp     short loc_180158AC3
0x180158a95  mov     edx, [rax]; uBytes
0x180158a97  mov     ecx, 40h ; '@'; uFlags
0x180158a9c  call    cs:__imp_LocalAlloc
0x180158aa2  mov     rbx, rax
0x180158aa5  test    rax, rax
0x180158aa8  jz      short loc_180158ADF
0x180158aaa  mov     rcx, [rsi]
0x180158aad  mov     edx, [rcx]
0x180158aaf  mov     [rax], edx
0x180158ab1  mov     rcx, [rsi]
0x180158ab4  mov     rdx, [rcx+8]
0x180158ab8  mov     [rax+8], rdx
0x180158abc  mov     [rax+10h], r15d
0x180158ac0  mov     [rsi], rbx
0x180158ac3  movzx   eax, dil
0x180158ac7  mov     rbx, [rsp+78h+arg_0]
0x180158acf  add     rsp, 40h
0x180158ad3  pop     r15
0x180158ad5  pop     r14
0x180158ad7  pop     r13
0x180158ad9  pop     r12
0x180158adb  pop     rdi
0x180158adc  pop     rsi
0x180158add  pop     rbp
0x180158ade  retn
0x180158adf  mov     ecx, 15B38Bh
0x180158ae4  call    MsoShipAssertTagProc
0x180158ae9  mov     dil, r12b
0x180158aec  jmp     short loc_180158AC0
0x180158aee  mov     ecx, 15B389h
0x180158af3  call    MsoShipAssertTagProc
0x180158af8  jmp     loc_180158A4B
```
