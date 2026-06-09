# SI_DISPATCH::Callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140004d10`
- end: `0x140004dd0`
- name: `?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `192`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, SI_DISPATCH *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140004d10`
- `0x140006a80`
- `0x14000cf3c`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x140004dc1`
- `ADVAPI32!RevertToSelf` at `0x140004dc1`
- `ADVAPI32!SetThreadToken` at `0x140004d2d`
- `ADVAPI32!SetThreadToken` at `0x140004d2d`
- `KERNEL32!SetLastError` at `0x140004d61`
- `KERNEL32!SetLastError` at `0x140004d61`
- `KERNEL32!GetLastError` at `0x140004da4`
- `KERNEL32!GetLastError` at `0x140004da4`

## pseudocode

```c
void __fastcall SI_DISPATCH::Callback(PTP_CALLBACK_INSTANCE Instance, SI_DISPATCH *Context, PTP_WORK Work)
{
  __int128 *v3; // rbp
  void *v5; // rdx
  int v6; // esi
  struct _SU_OBJECT *Object; // rax
  struct _SU_OBJECT *v8; // rbx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v12[20]; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+44h] [rbp-34h]

  v3 = (__int128 *)*((_QWORD *)Context + 2);
  v5 = (void *)*((_QWORD *)Context + 7);
  v6 = 0;
  if ( v5 )
  {
    if ( !SetThreadToken(0, v5) )
      return;
    v6 = 1;
  }
  Object = SI_DISPATCH::NextObject(Context);
  v8 = Object;
  if ( Object )
  {
    *((_DWORD *)Object + 5) = 1;
    if ( *(_DWORD *)Context != 3 )
    {
      SetLastError(0x57u);
LABEL_8:
      *((_DWORD *)v8 + 4) = GetLastError();
      *((_DWORD *)v8 + 5) = 2;
      goto LABEL_10;
    }
    v9 = *v3;
    *(_OWORD *)v12 = v3[1];
    v10 = *(_OWORD *)((char *)Object + 56);
    v11 = v9;
    v13 = HIDWORD(*((_QWORD *)v3 + 4));
    *(_OWORD *)&v12[4] = v10;
    if ( !(unsigned int)SiRefreshDrive((struct _SP_REFRESH_INFO *)&v11, Object, 0) )
      goto LABEL_8;
    *((_DWORD *)v8 + 5) = 3;
  }
LABEL_10:
  if ( v6 )
    RevertToSelf();
}

```

## disassembly

```asm
0x140004d10  push    rbx
0x140004d12  push    rbp
0x140004d13  push    rsi
0x140004d14  push    rdi
0x140004d15  sub     rsp, 58h
0x140004d19  mov     rbp, [rdx+10h]
0x140004d1d  mov     rdi, rdx
0x140004d20  mov     rdx, [rdx+38h]; Token
0x140004d24  xor     esi, esi
0x140004d26  test    rdx, rdx
0x140004d29  jz      short loc_140004D40
0x140004d2b  xor     ecx, ecx; Thread
0x140004d2d  call    cs:__imp_SetThreadToken
0x140004d33  test    eax, eax
0x140004d35  jz      loc_140004DC7
0x140004d3b  mov     esi, 1
0x140004d40  mov     rcx, rdi; this
0x140004d43  call    ?NextObject@SI_DISPATCH@@QEAAPEAU_SU_OBJECT@@XZ; SI_DISPATCH::NextObject(void)
0x140004d48  mov     rbx, rax
0x140004d4b  test    rax, rax
0x140004d4e  jz      short loc_140004DBD
0x140004d50  mov     dword ptr [rax+14h], 1
0x140004d57  cmp     dword ptr [rdi], 3
0x140004d5a  jz      short loc_140004D69
0x140004d5c  mov     ecx, 57h ; 'W'; dwErrCode
0x140004d61  call    cs:__imp_SetLastError
0x140004d67  jmp     short loc_140004DA4
0x140004d69  movups  xmm1, xmmword ptr [rbp+10h]
0x140004d6d  xor     r8d, r8d; int
0x140004d70  mov     rdx, rbx; struct _SU_DRIVE_OBJECT *
0x140004d73  movups  xmm0, xmmword ptr [rbp+0]
0x140004d77  lea     rcx, [rsp+78h+var_58]; struct _SP_REFRESH_INFO *
0x140004d7c  movups  [rsp+78h+var_48], xmm1
0x140004d81  movups  xmm1, xmmword ptr [rax+38h]
0x140004d85  movups  [rsp+78h+var_58], xmm0
0x140004d8a  movsd   xmm0, qword ptr [rbp+20h]
0x140004d8f  movsd   qword ptr [rsp+78h+var_38], xmm0
0x140004d95  movdqu  [rsp+78h+var_48+4], xmm1
0x140004d9b  call    ?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z; SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)
0x140004da0  test    eax, eax
0x140004da2  jnz     short loc_140004DB6
0x140004da4  call    cs:__imp_GetLastError
0x140004daa  mov     [rbx+10h], eax
0x140004dad  mov     dword ptr [rbx+14h], 2
0x140004db4  jmp     short loc_140004DBD
0x140004db6  mov     dword ptr [rbx+14h], 3
0x140004dbd  test    esi, esi
0x140004dbf  jz      short loc_140004DC7
0x140004dc1  call    cs:__imp_RevertToSelf
0x140004dc7  add     rsp, 58h
0x140004dcb  pop     rdi
0x140004dcc  pop     rsi
0x140004dcd  pop     rbp
0x140004dce  pop     rbx
0x140004dcf  retn
```
