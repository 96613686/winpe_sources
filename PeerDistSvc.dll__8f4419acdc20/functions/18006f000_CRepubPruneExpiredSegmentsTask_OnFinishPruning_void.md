# CRepubPruneExpiredSegmentsTask::OnFinishPruning(void)

- ea: `0x18006f000`
- end: `0x18006f203`
- name: `?OnFinishPruning@CRepubPruneExpiredSegmentsTask@@MEAAKXZ`
- size: `515`
- prototype: `unsigned int __fastcall(CRepubPruneExpiredSegmentsTask *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180008290`
- `0x1800082d0`
- `0x18000873c`
- `0x18004866c`
- `0x18006f000`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18006f0d4`
- `ESENT!JetPrepareUpdate` at `0x18006f0d4`
- `ESENT!JetSetColumns` at `0x18006f13d`
- `ESENT!JetSetColumns` at `0x18006f13d`
- `ESENT!JetUpdate` at `0x18006f185`
- `ESENT!JetUpdate` at `0x18006f185`

## pseudocode

```c
__int64 __fastcall CRepubPruneExpiredSegmentsTask::OnFinishPruning(CRepubPruneExpiredSegmentsTask *this)
{
  unsigned int v2; // edi
  int v3; // ecx
  __int64 v4; // rax
  unsigned int v5; // edi
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v2 = (*(__int64 (__fastcall **)(CRepubPruneExpiredSegmentsTask *))(*(_QWORD *)this + 80LL))(this);
  if ( !v2 )
  {
    v10 = GetCurrentTimeAsULONGLONG() / 0x2710;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 426, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    }
    v3 = *(_DWORD *)(*((_QWORD *)this + 51) + 568LL);
    v4 = *((_QWORD *)this + 50);
    *(_DWORD *)(v4 + 4) = 0;
    *(_QWORD *)(v4 + 20) = 0;
    *(_QWORD *)(v4 + 32) = 0;
    *(_DWORD *)v4 = v3;
    *(_QWORD *)(v4 + 8) = &v10;
    *(_DWORD *)(v4 + 16) = 8;
    *(_DWORD *)(v4 + 28) = 1;
    v5 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 80), 2u);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_12;
      }
      v7 = 427;
    }
    else
    {
      v5 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 80), *((JET_SETCOLUMN **)this + 50), 1u);
      if ( v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_12;
        }
        v7 = 428;
      }
      else
      {
        v5 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 80), 0, 0, 0);
        if ( !v5 )
        {
          v8 = CRepubCacheBackingStore::InitializeTTLExpiryPruning(*((CRepubCacheBackingStore **)this + 1));
          goto LABEL_24;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
LABEL_12:
          v8 = (*(__int64 (__fastcall **)(CRepubPruneExpiredSegmentsTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v5);
LABEL_24:
          v2 = v8;
          goto LABEL_25;
        }
        v7 = 429;
      }
    }
    WPP_SF_d(*((_QWORD *)v6 + 12), v7, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v5);
    goto LABEL_12;
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 430, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18006f000  push    rbx
0x18006f002  push    rdi
0x18006f003  push    r12
0x18006f005  push    r15
0x18006f007  sub     rsp, 38h
0x18006f00b  mov     rax, [rcx]
0x18006f00e  mov     rbx, rcx
0x18006f011  mov     rax, [rax+50h]
0x18006f015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f01a  lea     r15, WPP_GLOBAL_Control
0x18006f021  mov     edi, eax
0x18006f023  lea     r12, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18006f02a  test    eax, eax
0x18006f02c  jnz     loc_18006F1CA
0x18006f032  call    ?GetCurrentTimeAsULONGLONG@@YA_KXZ; GetCurrentTimeAsULONGLONG(void)
0x18006f037  mov     rcx, rax
0x18006f03a  mov     rax, 346DC5D63886594Bh
0x18006f044  mul     rcx
0x18006f047  mov     r9, rdx
0x18006f04a  shr     r9, 0Bh
0x18006f04e  mov     [rsp+58h+arg_0], r9
0x18006f053  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f05a  cmp     rcx, r15
0x18006f05d  jz      short loc_18006F07C
0x18006f05f  test    byte ptr [rcx+6Ch], 4
0x18006f063  jz      short loc_18006F07C
0x18006f065  cmp     byte ptr [rcx+69h], 4
0x18006f069  jb      short loc_18006F07C
0x18006f06b  mov     rcx, [rcx+60h]
0x18006f06f  mov     edx, 1AAh
0x18006f074  mov     r8, r12
0x18006f077  call    WPP_SF_q
0x18006f07c  mov     rax, [rbx+198h]
0x18006f083  mov     r8d, 2; prep
0x18006f089  mov     ecx, [rax+238h]
0x18006f08f  mov     rax, [rbx+190h]
0x18006f096  mov     dword ptr [rax+4], 0
0x18006f09d  mov     qword ptr [rax+14h], 0
0x18006f0a5  mov     qword ptr [rax+20h], 0
0x18006f0ad  mov     [rax], ecx
0x18006f0af  lea     rcx, [rsp+58h+arg_0]
0x18006f0b4  mov     [rax+8], rcx
0x18006f0b8  mov     dword ptr [rax+10h], 8
0x18006f0bf  mov     dword ptr [rax+1Ch], 1
0x18006f0c6  mov     rdx, [rbx+280h]; tableid
0x18006f0cd  mov     rcx, [rbx+178h]; sesid
0x18006f0d4  call    cs:__imp_JetPrepareUpdate
0x18006f0da  mov     edi, eax
0x18006f0dc  test    eax, eax
0x18006f0de  jz      short loc_18006F122
0x18006f0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f0e7  cmp     rcx, r15
0x18006f0ea  jz      short loc_18006F10C
0x18006f0ec  test    byte ptr [rcx+6Ch], 4
0x18006f0f0  jz      short loc_18006F10C
0x18006f0f2  cmp     byte ptr [rcx+69h], 1
0x18006f0f6  jb      short loc_18006F10C
0x18006f0f8  mov     edx, 1ABh
0x18006f0fd  mov     rcx, [rcx+60h]
0x18006f101  mov     r9d, edi
0x18006f104  mov     r8, r12
0x18006f107  call    WPP_SF_d
0x18006f10c  mov     rax, [rbx]
0x18006f10f  mov     edx, edi
0x18006f111  mov     rcx, rbx
0x18006f114  mov     rax, [rax+30h]
0x18006f118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f11d  jmp     loc_18006F1C8
0x18006f122  mov     r8, [rbx+190h]; psetcolumn
0x18006f129  mov     r9d, 1; csetcolumn
0x18006f12f  mov     rdx, [rbx+280h]; tableid
0x18006f136  mov     rcx, [rbx+178h]; sesid
0x18006f13d  call    cs:__imp_JetSetColumns
0x18006f143  mov     edi, eax
0x18006f145  test    eax, eax
0x18006f147  jz      short loc_18006F168
0x18006f149  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f150  cmp     rcx, r15
0x18006f153  jz      short loc_18006F10C
0x18006f155  test    byte ptr [rcx+6Ch], 4
0x18006f159  jz      short loc_18006F10C
0x18006f15b  cmp     byte ptr [rcx+69h], 1
0x18006f15f  jb      short loc_18006F10C
0x18006f161  mov     edx, 1ACh
0x18006f166  jmp     short loc_18006F0FD
0x18006f168  mov     rdx, [rbx+280h]; tableid
0x18006f16f  xor     r9d, r9d; cbBookmark
0x18006f172  mov     rcx, [rbx+178h]; sesid
0x18006f179  xor     r8d, r8d; pvBookmark
0x18006f17c  mov     [rsp+58h+pcbActual], 0; pcbActual
0x18006f185  call    cs:__imp_JetUpdate
0x18006f18b  mov     edi, eax
0x18006f18d  test    eax, eax
0x18006f18f  jz      short loc_18006F1BF
0x18006f191  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f198  cmp     rcx, r15
0x18006f19b  jz      loc_18006F10C
0x18006f1a1  test    byte ptr [rcx+6Ch], 4
0x18006f1a5  jz      loc_18006F10C
0x18006f1ab  cmp     byte ptr [rcx+69h], 1
0x18006f1af  jb      loc_18006F10C
0x18006f1b5  mov     edx, 1ADh
0x18006f1ba  jmp     loc_18006F0FD
0x18006f1bf  mov     rcx, [rbx+8]; this
0x18006f1c3  call    ?InitializeTTLExpiryPruning@CRepubCacheBackingStore@@QEAAKXZ; CRepubCacheBackingStore::InitializeTTLExpiryPruning(void)
0x18006f1c8  mov     edi, eax
0x18006f1ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f1d1  cmp     rcx, r15
0x18006f1d4  jz      short loc_18006F1F6
0x18006f1d6  test    byte ptr [rcx+6Ch], 4
0x18006f1da  jz      short loc_18006F1F6
0x18006f1dc  cmp     byte ptr [rcx+69h], 4
0x18006f1e0  jb      short loc_18006F1F6
0x18006f1e2  mov     rcx, [rcx+60h]
0x18006f1e6  mov     edx, 1AEh
0x18006f1eb  mov     r9d, edi
0x18006f1ee  mov     r8, r12
0x18006f1f1  call    WPP_SF_d
0x18006f1f6  mov     eax, edi
0x18006f1f8  add     rsp, 38h
0x18006f1fc  pop     r15
0x18006f1fe  pop     r12
0x18006f200  pop     rdi
0x18006f201  pop     rbx
0x18006f202  retn
```
