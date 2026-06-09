# CPubEvictPublicationsTask::MarkPublicationDeleted(unsigned __int64,ulong)

- ea: `0x18008e948`
- end: `0x18008eb1a`
- name: `?MarkPublicationDeleted@CPubEvictPublicationsTask@@AEAAK_KK@Z`
- size: `466`
- prototype: `unsigned int __fastcall(CPubEvictPublicationsTask *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18008c6d0`

## callees

- `0x1800082d0`
- `0x18000ceac`
- `0x18008e948`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18008e9f6`
- `ESENT!JetPrepareUpdate` at `0x18008e9f6`
- `ESENT!JetSetColumns` at `0x18008ea5e`
- `ESENT!JetSetColumns` at `0x18008ea5e`
- `ESENT!JetUpdate` at `0x18008eabb`
- `ESENT!JetUpdate` at `0x18008eabb`

## pseudocode

```c
__int64 __fastcall CPubEvictPublicationsTask::MarkPublicationDeleted(
        CPubEvictPublicationsTask *this,
        __int64 a2,
        int a3)
{
  __int64 v4; // rax
  int v5; // ecx
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // edi
  CHostedCacheMsgEncoding *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = a3;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 125, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
    a3 = v14;
  }
  v4 = *((_QWORD *)this + 51);
  v14 = a3 | 2;
  v5 = *(_DWORD *)(v4 + 688);
  v6 = *((_QWORD *)this + 50);
  *(_DWORD *)(v6 + 4) = 0;
  *(_QWORD *)(v6 + 20) = 0;
  *(_QWORD *)(v6 + 32) = 0;
  *(_DWORD *)v6 = v5;
  *(_QWORD *)(v6 + 8) = &v14;
  *(_DWORD *)(v6 + 16) = 4;
  *(_DWORD *)(v6 + 28) = 1;
  v7 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 2u);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(CPubEvictPublicationsTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v7);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v10 = 126;
LABEL_20:
      WPP_SF_Dd(*((_QWORD *)v9 + 12), v10, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
    }
  }
  else
  {
    v11 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_SETCOLUMN **)this + 50), 1u);
    if ( v11 )
    {
      v8 = (*(__int64 (__fastcall **)(CPubEvictPublicationsTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v11);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v10 = 127;
        goto LABEL_20;
      }
    }
    else
    {
      v8 = 0;
      v12 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
      if ( v12 )
      {
        v8 = (*(__int64 (__fastcall **)(CPubEvictPublicationsTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v12);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v10 = 128;
          goto LABEL_20;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18008e948  mov     [rsp+arg_10], r8d
0x18008e94d  push    rbx
0x18008e94e  push    rsi
0x18008e94f  push    rdi
0x18008e950  push    r13
0x18008e952  sub     rsp, 38h
0x18008e956  mov     r9, rdx
0x18008e959  mov     rbx, rcx
0x18008e95c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e963  lea     r13, WPP_GLOBAL_Control
0x18008e96a  cmp     rcx, r13
0x18008e96d  jz      short loc_18008E995
0x18008e96f  test    byte ptr [rcx+6Ch], 4
0x18008e973  jz      short loc_18008E995
0x18008e975  cmp     byte ptr [rcx+69h], 4
0x18008e979  jb      short loc_18008E995
0x18008e97b  mov     rcx, [rcx+60h]
0x18008e97f  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008e986  mov     edx, 7Dh ; '}'
0x18008e98b  call    WPP_SF_q
0x18008e990  mov     r8d, [rsp+58h+arg_10]
0x18008e995  mov     rax, [rbx+198h]
0x18008e99c  or      r8d, 2
0x18008e9a0  mov     [rsp+58h+arg_10], r8d
0x18008e9a5  mov     r8d, 2; prep
0x18008e9ab  mov     ecx, [rax+2B0h]
0x18008e9b1  mov     rax, [rbx+190h]
0x18008e9b8  mov     dword ptr [rax+4], 0
0x18008e9bf  mov     qword ptr [rax+14h], 0
0x18008e9c7  mov     qword ptr [rax+20h], 0
0x18008e9cf  mov     [rax], ecx
0x18008e9d1  lea     rcx, [rsp+58h+arg_10]
0x18008e9d6  mov     [rax+8], rcx
0x18008e9da  mov     dword ptr [rax+10h], 4
0x18008e9e1  mov     dword ptr [rax+1Ch], 1
0x18008e9e8  mov     rdx, [rbx+1A8h]; tableid
0x18008e9ef  mov     rcx, [rbx+178h]; sesid
0x18008e9f6  call    cs:__imp_JetPrepareUpdate
0x18008e9fc  mov     esi, eax
0x18008e9fe  test    eax, eax
0x18008ea00  jz      short loc_18008EA43
0x18008ea02  mov     rcx, [rbx]
0x18008ea05  mov     edx, esi
0x18008ea07  mov     rax, [rcx+18h]
0x18008ea0b  mov     rcx, rbx
0x18008ea0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea13  mov     edi, eax
0x18008ea15  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea1c  cmp     rcx, r13
0x18008ea1f  jz      loc_18008EB0E
0x18008ea25  test    byte ptr [rcx+6Ch], 4
0x18008ea29  jz      loc_18008EB0E
0x18008ea2f  cmp     byte ptr [rcx+69h], 1
0x18008ea33  jb      loc_18008EB0E
0x18008ea39  mov     edx, 7Eh ; '~'
0x18008ea3e  jmp     loc_18008EAF7
0x18008ea43  mov     r8, [rbx+190h]; psetcolumn
0x18008ea4a  mov     r9d, 1; csetcolumn
0x18008ea50  mov     rdx, [rbx+1A8h]; tableid
0x18008ea57  mov     rcx, [rbx+178h]; sesid
0x18008ea5e  call    cs:__imp_JetSetColumns
0x18008ea64  mov     esi, eax
0x18008ea66  test    eax, eax
0x18008ea68  jz      short loc_18008EAA0
0x18008ea6a  mov     rcx, [rbx]
0x18008ea6d  mov     edx, esi
0x18008ea6f  mov     rax, [rcx+18h]
0x18008ea73  mov     rcx, rbx
0x18008ea76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea7b  mov     edi, eax
0x18008ea7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea84  cmp     rcx, r13
0x18008ea87  jz      loc_18008EB0E
0x18008ea8d  test    byte ptr [rcx+6Ch], 4
0x18008ea91  jz      short loc_18008EB0E
0x18008ea93  cmp     byte ptr [rcx+69h], 1
0x18008ea97  jb      short loc_18008EB0E
0x18008ea99  mov     edx, 7Fh
0x18008ea9e  jmp     short loc_18008EAF7
0x18008eaa0  mov     rdx, [rbx+1A8h]; tableid
0x18008eaa7  xor     edi, edi
0x18008eaa9  mov     rcx, [rbx+178h]; sesid
0x18008eab0  xor     r9d, r9d; cbBookmark
0x18008eab3  xor     r8d, r8d; pvBookmark
0x18008eab6  mov     [rsp+58h+pcbActual], rdi; pcbActual
0x18008eabb  call    cs:__imp_JetUpdate
0x18008eac1  mov     esi, eax
0x18008eac3  test    eax, eax
0x18008eac5  jz      short loc_18008EB0E
0x18008eac7  mov     rcx, [rbx]
0x18008eaca  mov     edx, esi
0x18008eacc  mov     rax, [rcx+18h]
0x18008ead0  mov     rcx, rbx
0x18008ead3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ead8  mov     edi, eax
0x18008eada  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eae1  cmp     rcx, r13
0x18008eae4  jz      short loc_18008EB0E
0x18008eae6  test    byte ptr [rcx+6Ch], 4
0x18008eaea  jz      short loc_18008EB0E
0x18008eaec  cmp     byte ptr [rcx+69h], 1
0x18008eaf0  jb      short loc_18008EB0E
0x18008eaf2  mov     edx, 80h
0x18008eaf7  mov     rcx, [rcx+60h]
0x18008eafb  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008eb02  mov     r9d, esi
0x18008eb05  mov     dword ptr [rsp+58h+pcbActual], eax
0x18008eb09  call    WPP_SF_Dd
0x18008eb0e  mov     eax, edi
0x18008eb10  add     rsp, 38h
0x18008eb14  pop     r13
0x18008eb16  pop     rdi
0x18008eb17  pop     rsi
0x18008eb18  pop     rbx
0x18008eb19  retn
```
