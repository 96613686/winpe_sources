# CRepubCacheStagedContentWriteTask::CreateStagedContentRecord(unsigned __int64,ulong)

- ea: `0x18007ce10`
- end: `0x18007d02b`
- name: `?CreateStagedContentRecord@CRepubCacheStagedContentWriteTask@@AEAAK_KK@Z`
- size: `539`
- prototype: `unsigned int __fastcall(CRepubCacheStagedContentWriteTask *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18007ef00`

## callees

- `0x18000ceac`
- `0x18007ce10`
- `0x18007d940`
- `0x180086fdc`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18007cefe`
- `ESENT!JetPrepareUpdate` at `0x18007cefe`
- `ESENT!JetSetColumns` at `0x18007cf68`
- `ESENT!JetSetColumns` at `0x18007cf68`
- `ESENT!JetUpdate` at `0x18007cfc5`
- `ESENT!JetUpdate` at `0x18007cfc5`

## pseudocode

```c
__int64 __fastcall CRepubCacheStagedContentWriteTask::CreateStagedContentRecord(
        CRepubCacheStagedContentWriteTask *this,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int csetcolumn; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int64 v12; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v12 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_IDID(*((_QWORD *)WPP_GLOBAL_Control + 12), a2, a3, *((_QWORD *)this + 84), *((__int16 *)this + 296), a2, a3);
  }
  csetcolumn = *((_DWORD *)this + 96);
  CRepubCacheStagedContentWriteTask::InitializeStagedContentTableSetColumns(
    this,
    (unsigned __int64 *)this + 84,
    &v12,
    &v13,
    (__int16 *)this + 296,
    (char *)this + 680,
    (unsigned __int64 *)this + 78,
    (unsigned int *)this + 158,
    (unsigned int *)this + 159,
    *((struct JET_SETCOLUMN **)this + 50),
    &csetcolumn);
  v4 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 87), 0);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(CRepubCacheStagedContentWriteTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v4);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v7 = 297;
LABEL_20:
      WPP_SF_Dd(*((_QWORD *)v6 + 12), v7, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
    }
  }
  else
  {
    v8 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 87), *((JET_SETCOLUMN **)this + 50), csetcolumn);
    if ( v8 )
    {
      v5 = (*(__int64 (__fastcall **)(CRepubCacheStagedContentWriteTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v8);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v7 = 298;
        goto LABEL_20;
      }
    }
    else
    {
      v5 = 0;
      v9 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 87), 0, 0, 0);
      if ( v9 )
      {
        v5 = (*(__int64 (__fastcall **)(CRepubCacheStagedContentWriteTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v9);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v7 = 299;
          goto LABEL_20;
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18007ce10  mov     r11, rsp
0x18007ce13  mov     [r11+20h], rbx
0x18007ce17  mov     [r11+18h], r8d
0x18007ce1b  mov     [r11+10h], rdx
0x18007ce1f  push    rsi
0x18007ce20  push    rdi
0x18007ce21  push    r14
0x18007ce23  sub     rsp, 60h
0x18007ce27  mov     rbx, rcx
0x18007ce2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce31  lea     r14, WPP_GLOBAL_Control
0x18007ce38  cmp     rcx, r14
0x18007ce3b  jz      short loc_18007CE6C
0x18007ce3d  test    byte ptr [rcx+6Ch], 4
0x18007ce41  jz      short loc_18007CE6C
0x18007ce43  cmp     byte ptr [rcx+69h], 4
0x18007ce47  jb      short loc_18007CE6C
0x18007ce49  movsx   eax, word ptr [rbx+250h]
0x18007ce50  mov     r9, [rbx+2A0h]
0x18007ce57  mov     rcx, [rcx+60h]
0x18007ce5b  mov     [r11-48h], r8d
0x18007ce5f  mov     [r11-50h], rdx
0x18007ce63  mov     dword ptr [rsp+78h+pcbActual], eax
0x18007ce67  call    WPP_SF_IDID
0x18007ce6c  mov     eax, [rbx+180h]
0x18007ce72  lea     rcx, [rbx+27Ch]
0x18007ce79  mov     [rsp+78h+csetcolumn], eax
0x18007ce80  lea     r8, [rbx+278h]
0x18007ce87  lea     rax, [rsp+78h+csetcolumn]
0x18007ce8f  mov     [rsp+78h+var_28], rax; unsigned int *
0x18007ce94  lea     r9, [rbx+270h]
0x18007ce9b  mov     rax, [rbx+190h]
0x18007cea2  lea     r10, [rbx+2A8h]
0x18007cea9  mov     [rsp+78h+var_30], rax; struct JET_SETCOLUMN *
0x18007ceae  lea     r11, [rbx+250h]
0x18007ceb5  mov     [rsp+78h+var_38], rcx; unsigned int *
0x18007ceba  lea     rdx, [rbx+2A0h]; unsigned __int64 *
0x18007cec1  mov     [rsp+78h+var_40], r8; unsigned int *
0x18007cec6  mov     rcx, rbx; this
0x18007cec9  mov     [rsp+78h+var_48], r9; unsigned __int64 *
0x18007cece  lea     r8, [rsp+78h+arg_8]; unsigned __int64 *
0x18007ced6  mov     [rsp+78h+var_50], r10; void *
0x18007cedb  lea     r9, [rsp+78h+arg_10]; unsigned int *
0x18007cee3  mov     [rsp+78h+pcbActual], r11; __int16 *
0x18007cee8  call    ?InitializeStagedContentTableSetColumns@CRepubCacheStagedContentWriteTask@@AEAAXPEA_K0PEAKPEAFPEAX011PEAUJET_SETCOLUMN@@1@Z; CRepubCacheStagedContentWriteTask::InitializeStagedContentTableSetColumns(unsigned __int64 *,unsigned __int64 *,ulong *,short *,void *,unsigned __int64 *,ulong *,ulong *,JET_SETCOLUMN *,ulong *)
0x18007ceed  mov     rdx, [rbx+2B8h]; tableid
0x18007cef4  xor     r8d, r8d; prep
0x18007cef7  mov     rcx, [rbx+178h]; sesid
0x18007cefe  call    cs:__imp_JetPrepareUpdate
0x18007cf04  mov     esi, eax
0x18007cf06  test    eax, eax
0x18007cf08  jz      short loc_18007CF4B
0x18007cf0a  mov     rcx, [rbx]
0x18007cf0d  mov     edx, esi
0x18007cf0f  mov     rax, [rcx+30h]
0x18007cf13  mov     rcx, rbx
0x18007cf16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf1b  mov     edi, eax
0x18007cf1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf24  cmp     rcx, r14
0x18007cf27  jz      loc_18007D018
0x18007cf2d  test    byte ptr [rcx+6Ch], 4
0x18007cf31  jz      loc_18007D018
0x18007cf37  cmp     byte ptr [rcx+69h], 1
0x18007cf3b  jb      loc_18007D018
0x18007cf41  mov     edx, 129h
0x18007cf46  jmp     loc_18007D001
0x18007cf4b  mov     r9d, [rsp+78h+csetcolumn]; csetcolumn
0x18007cf53  mov     r8, [rbx+190h]; psetcolumn
0x18007cf5a  mov     rdx, [rbx+2B8h]; tableid
0x18007cf61  mov     rcx, [rbx+178h]; sesid
0x18007cf68  call    cs:__imp_JetSetColumns
0x18007cf6e  mov     esi, eax
0x18007cf70  test    eax, eax
0x18007cf72  jz      short loc_18007CFAA
0x18007cf74  mov     rcx, [rbx]
0x18007cf77  mov     edx, esi
0x18007cf79  mov     rax, [rcx+30h]
0x18007cf7d  mov     rcx, rbx
0x18007cf80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf85  mov     edi, eax
0x18007cf87  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf8e  cmp     rcx, r14
0x18007cf91  jz      loc_18007D018
0x18007cf97  test    byte ptr [rcx+6Ch], 4
0x18007cf9b  jz      short loc_18007D018
0x18007cf9d  cmp     byte ptr [rcx+69h], 1
0x18007cfa1  jb      short loc_18007D018
0x18007cfa3  mov     edx, 12Ah
0x18007cfa8  jmp     short loc_18007D001
0x18007cfaa  mov     rdx, [rbx+2B8h]; tableid
0x18007cfb1  xor     edi, edi
0x18007cfb3  mov     rcx, [rbx+178h]; sesid
0x18007cfba  xor     r9d, r9d; cbBookmark
0x18007cfbd  xor     r8d, r8d; pvBookmark
0x18007cfc0  mov     [rsp+78h+pcbActual], rdi; pcbActual
0x18007cfc5  call    cs:__imp_JetUpdate
0x18007cfcb  mov     esi, eax
0x18007cfcd  test    eax, eax
0x18007cfcf  jz      short loc_18007D018
0x18007cfd1  mov     rcx, [rbx]
0x18007cfd4  mov     edx, esi
0x18007cfd6  mov     rax, [rcx+30h]
0x18007cfda  mov     rcx, rbx
0x18007cfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfe2  mov     edi, eax
0x18007cfe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cfeb  cmp     rcx, r14
0x18007cfee  jz      short loc_18007D018
0x18007cff0  test    byte ptr [rcx+6Ch], 4
0x18007cff4  jz      short loc_18007D018
0x18007cff6  cmp     byte ptr [rcx+69h], 1
0x18007cffa  jb      short loc_18007D018
0x18007cffc  mov     edx, 12Bh
0x18007d001  mov     rcx, [rcx+60h]
0x18007d005  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007d00c  mov     r9d, esi
0x18007d00f  mov     dword ptr [rsp+78h+pcbActual], eax
0x18007d013  call    WPP_SF_Dd
0x18007d018  mov     rbx, [rsp+78h+arg_18]
0x18007d020  mov     eax, edi
0x18007d022  add     rsp, 60h
0x18007d026  pop     r14
0x18007d028  pop     rdi
0x18007d029  pop     rsi
0x18007d02a  retn
```
