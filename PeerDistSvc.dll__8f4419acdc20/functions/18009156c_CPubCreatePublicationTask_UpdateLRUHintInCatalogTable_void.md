# CPubCreatePublicationTask::UpdateLRUHintInCatalogTable(void)

- ea: `0x18009156c`
- end: `0x18009176f`
- name: `?UpdateLRUHintInCatalogTable@CPubCreatePublicationTask@@IEAAKXZ`
- size: `515`
- prototype: `unsigned int __fastcall(CPubCreatePublicationTask *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18008e3f0`

## callees

- `0x1800082d0`
- `0x18000ceac`
- `0x18009156c`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18009162b`
- `ESENT!JetPrepareUpdate` at `0x18009162b`
- `ESENT!JetSetColumns` at `0x180091697`
- `ESENT!JetSetColumns` at `0x180091697`
- `ESENT!JetUpdate` at `0x180091703`
- `ESENT!JetUpdate` at `0x180091703`

## pseudocode

```c
__int64 __fastcall CPubCreatePublicationTask::UpdateLRUHintInCatalogTable(CPubCreatePublicationTask *this)
{
  __int64 v1; // rdx
  __int64 v3; // r9
  JET_TABLEID v4; // rdx
  JET_SESID v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  CHostedCacheMsgEncoding *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+90h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 1);
  memset(&psetcolumn, 0, sizeof(psetcolumn));
  v3 = *(_QWORD *)(v1 + 248);
  *(_QWORD *)(v1 + 248) = v3 + 1;
  v14 = v3;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
  }
  v4 = *((_QWORD *)this + 53);
  psetcolumn.columnid = *(_DWORD *)(*((_QWORD *)this + 51) + 684LL);
  v5 = *((_QWORD *)this + 47);
  psetcolumn.pvData = &v14;
  *(&psetcolumn.columnid + 1) = 0;
  *(_QWORD *)&psetcolumn.grbit = 0;
  *(_QWORD *)&psetcolumn.err = 0;
  psetcolumn.cbData = 8;
  psetcolumn.itagSequence = 1;
  v6 = JetPrepareUpdate(v5, v4, 4u);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v6);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v9 = 57;
LABEL_21:
      WPP_SF_Dd(*((_QWORD *)v8 + 12), v9, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
    }
  }
  else
  {
    v10 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), &psetcolumn, 1u);
    if ( v10 )
    {
      v7 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v10);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v9 = 58;
        goto LABEL_21;
      }
    }
    else
    {
      v7 = 0;
      v11 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
      if ( v11 != -1102 )
      {
        if ( v11 )
        {
          v7 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v11);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v9 = 59;
            goto LABEL_21;
          }
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18009156c  push    rbp
0x18009156e  push    rbx
0x18009156f  push    rsi
0x180091570  push    rdi
0x180091571  mov     rbp, rsp
0x180091574  sub     rsp, 68h
0x180091578  mov     rdx, [rcx+8]
0x18009157c  xorps   xmm0, xmm0
0x18009157f  xor     eax, eax
0x180091581  mov     rdi, rcx
0x180091584  mov     qword ptr [rbp+psetcolumn.err], rax
0x180091588  movups  xmmword ptr [rbp+psetcolumn.columnid], xmm0
0x18009158c  movups  xmmword ptr [rbp+psetcolumn.cbData], xmm0
0x180091590  mov     r9, [rdx+0F8h]
0x180091597  lea     rax, [r9+1]
0x18009159b  mov     [rdx+0F8h], rax
0x1800915a2  mov     [rbp+arg_0], r9
0x1800915a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800915ad  lea     rax, WPP_GLOBAL_Control
0x1800915b4  cmp     rcx, rax
0x1800915b7  jz      short loc_1800915DA
0x1800915b9  test    byte ptr [rcx+6Ch], 4
0x1800915bd  jz      short loc_1800915DA
0x1800915bf  cmp     byte ptr [rcx+69h], 4
0x1800915c3  jb      short loc_1800915DA
0x1800915c5  mov     rcx, [rcx+60h]
0x1800915c9  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x1800915d0  mov     edx, 38h ; '8'
0x1800915d5  call    WPP_SF_q
0x1800915da  mov     rax, [rdi+198h]
0x1800915e1  mov     r8d, 4; prep
0x1800915e7  mov     rdx, [rdi+1A8h]; tableid
0x1800915ee  mov     ecx, [rax+2ACh]
0x1800915f4  lea     rax, [rbp+arg_0]
0x1800915f8  mov     [rbp+psetcolumn.columnid], ecx
0x1800915fb  mov     rcx, [rdi+178h]; sesid
0x180091602  mov     [rbp+psetcolumn.pvData], rax
0x180091606  mov     dword ptr [rbp+psetcolumn+4], 0
0x18009160d  mov     qword ptr [rbp+psetcolumn.grbit], 0
0x180091615  mov     qword ptr [rbp+psetcolumn.err], 0
0x18009161d  mov     [rbp+psetcolumn.cbData], 8
0x180091624  mov     [rbp+psetcolumn.itagSequence], 1
0x18009162b  call    cs:__imp_JetPrepareUpdate
0x180091631  mov     esi, eax
0x180091633  test    eax, eax
0x180091635  jz      short loc_18009167F
0x180091637  mov     rcx, [rdi]
0x18009163a  mov     edx, esi
0x18009163c  mov     rax, [rcx+18h]
0x180091640  mov     rcx, rdi
0x180091643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091648  mov     ebx, eax
0x18009164a  mov     rcx, cs:WPP_GLOBAL_Control
0x180091651  lea     rax, WPP_GLOBAL_Control
0x180091658  cmp     rcx, rax
0x18009165b  jz      loc_180091764
0x180091661  test    byte ptr [rcx+6Ch], 4
0x180091665  jz      loc_180091764
0x18009166b  cmp     byte ptr [rcx+69h], 1
0x18009166f  jb      loc_180091764
0x180091675  mov     edx, 39h ; '9'
0x18009167a  jmp     loc_18009174D
0x18009167f  mov     rdx, [rdi+1A8h]; tableid
0x180091686  lea     r8, [rbp+psetcolumn]; psetcolumn
0x18009168a  mov     rcx, [rdi+178h]; sesid
0x180091691  mov     r9d, 1; csetcolumn
0x180091697  call    cs:__imp_JetSetColumns
0x18009169d  mov     esi, eax
0x18009169f  test    eax, eax
0x1800916a1  jz      short loc_1800916E8
0x1800916a3  mov     rcx, [rdi]
0x1800916a6  mov     edx, esi
0x1800916a8  mov     rax, [rcx+18h]
0x1800916ac  mov     rcx, rdi
0x1800916af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800916b4  mov     ebx, eax
0x1800916b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800916bd  lea     rax, WPP_GLOBAL_Control
0x1800916c4  cmp     rcx, rax
0x1800916c7  jz      loc_180091764
0x1800916cd  test    byte ptr [rcx+6Ch], 4
0x1800916d1  jz      loc_180091764
0x1800916d7  cmp     byte ptr [rcx+69h], 1
0x1800916db  jb      loc_180091764
0x1800916e1  mov     edx, 3Ah ; ':'
0x1800916e6  jmp     short loc_18009174D
0x1800916e8  mov     rdx, [rdi+1A8h]; tableid
0x1800916ef  xor     ebx, ebx
0x1800916f1  mov     rcx, [rdi+178h]; sesid
0x1800916f8  xor     r9d, r9d; cbBookmark
0x1800916fb  xor     r8d, r8d; pvBookmark
0x1800916fe  mov     [rsp+68h+pcbActual], rbx; pcbActual
0x180091703  call    cs:__imp_JetUpdate
0x180091709  mov     esi, eax
0x18009170b  cmp     eax, 0FFFFFBB2h
0x180091710  jz      short loc_180091764
0x180091712  test    eax, eax
0x180091714  jz      short loc_180091764
0x180091716  mov     rcx, [rdi]
0x180091719  mov     edx, esi
0x18009171b  mov     rax, [rcx+18h]
0x18009171f  mov     rcx, rdi
0x180091722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091727  mov     ebx, eax
0x180091729  mov     rcx, cs:WPP_GLOBAL_Control
0x180091730  lea     rax, WPP_GLOBAL_Control
0x180091737  cmp     rcx, rax
0x18009173a  jz      short loc_180091764
0x18009173c  test    byte ptr [rcx+6Ch], 4
0x180091740  jz      short loc_180091764
0x180091742  cmp     byte ptr [rcx+69h], 1
0x180091746  jb      short loc_180091764
0x180091748  mov     edx, 3Bh ; ';'
0x18009174d  mov     rcx, [rcx+60h]
0x180091751  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x180091758  mov     r9d, esi
0x18009175b  mov     dword ptr [rsp+68h+pcbActual], ebx
0x18009175f  call    WPP_SF_Dd
0x180091764  mov     eax, ebx
0x180091766  add     rsp, 68h
0x18009176a  pop     rdi
0x18009176b  pop     rsi
0x18009176c  pop     rbx
0x18009176d  pop     rbp
0x18009176e  retn
```
