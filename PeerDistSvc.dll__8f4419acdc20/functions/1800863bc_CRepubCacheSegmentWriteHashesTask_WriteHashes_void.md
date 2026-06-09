# CRepubCacheSegmentWriteHashesTask::WriteHashes(void)

- ea: `0x1800863bc`
- end: `0x180086c42`
- name: `?WriteHashes@CRepubCacheSegmentWriteHashesTask@@AEAAKXZ`
- size: `2182`
- prototype: `unsigned int __fastcall(CRepubCacheSegmentWriteHashesTask *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18007eb90`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180008290`
- `0x1800082d0`
- `0x18000ceac`
- `0x18000fac0`
- `0x180011798`
- `0x18001f0ac`
- `0x18002a8bc`
- `0x1800521d8`
- `0x1800645bc`
- `0x180065af8`
- `0x18007ae84`
- `0x18007b5b0`
- `0x1800863bc`
- `0x180092c40`
- `0x180144882`
- `0x180159010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18008668b`
- `msvcrt!memcpy_s` at `0x1800868e5`
- `msvcrt!memcpy_s` at `0x18008668b`
- `msvcrt!memcpy_s` at `0x1800868e5`
- `ESENT!JetPrepareUpdate` at `0x180086a36`
- `ESENT!JetPrepareUpdate` at `0x180086a36`
- `ESENT!JetSetColumns` at `0x180086aa7`
- `ESENT!JetSetColumns` at `0x180086aa7`
- `ESENT!JetRetrieveColumns` at `0x18008685f`
- `ESENT!JetRetrieveColumns` at `0x18008685f`
- `ESENT!JetUpdate` at `0x180086b16`
- `ESENT!JetUpdate` at `0x180086b16`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRepubCacheSegmentWriteHashesTask::WriteHashes(CRepubCacheSegmentWriteHashesTask *this)
{
  unsigned __int16 v2; // ax
  unsigned __int64 v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // r9
  unsigned __int64 v6; // r13
  unsigned int v7; // r15d
  unsigned __int64 v8; // r12
  void *v9; // rbx
  void *v10; // rdi
  char *v11; // rsi
  __int64 v12; // rcx
  unsigned int First; // r15d
  CHostedCacheMsgEncoding *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r15
  __int16 v18; // r15
  CHostedCacheMsgEncoding *v19; // rcx
  void *v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rax
  unsigned int Columns; // eax
  CHostedCacheMsgEncoding *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // eax
  CHostedCacheMsgEncoding *v29; // rcx
  int v30; // ecx
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  rsize_t SourceSize; // [rsp+40h] [rbp-59h] BYREF
  __int16 v39; // [rsp+48h] [rbp-51h]
  void *v40; // [rsp+50h] [rbp-49h] BYREF
  char v41; // [rsp+58h] [rbp-41h]
  void *v42; // [rsp+60h] [rbp-39h] BYREF
  void *Source; // [rsp+68h] [rbp-31h]
  size_t Size; // [rsp+70h] [rbp-29h]
  _QWORD v45[15]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 v46; // [rsp+100h] [rbp+67h]
  unsigned __int64 v47; // [rsp+100h] [rbp+67h]
  unsigned int v48; // [rsp+108h] [rbp+6Fh]
  unsigned int v49; // [rsp+110h] [rbp+77h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 203, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
  }
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 52) + 24LL) + 96LL))(*((_QWORD *)this + 52) + 24LL);
  v3 = v2;
  v46 = v2;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 52) + 24LL) + 88LL))(*((_QWORD *)this + 52) + 24LL);
  v48 = v4;
  v5 = *((_QWORD *)this + 54);
  v6 = *(_QWORD *)(v5 + 72);
  v7 = *(_DWORD *)(v5 + 60);
  v49 = v7;
  if ( v6 <= 0xFFFFFFFF && !(v6 % v3) && !(v7 % (unsigned int)v3) )
  {
    Size = v4;
    if ( v6 <= v4 && v7 <= v4 )
    {
      SourceSize = v7;
      if ( v6 + v7 <= v4 )
      {
        Source = *(void **)(v5 + 64);
        v8 = ((*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 52) + 16LL))(*((_QWORD *)this + 52)) + 7) >> 3;
        v9 = operator new[](v8);
        v45[4] = v9;
        memset_0(v9, 0, (unsigned int)v8);
        v10 = operator new[]((unsigned int)v8);
        v45[5] = v10;
        memset_0(v10, 0, (unsigned int)v8);
        v11 = 0;
        v42 = 0;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_qDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            205,
            WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
            v6,
            v7,
            v46,
            v48);
        }
        v12 = *(_QWORD *)(*((_QWORD *)this + 53) + 24LL);
        v45[0] = &CCatalogTableSegmentIdIterator::`vftable';
        v45[2] = *((_QWORD *)this + 47);
        v45[3] = *((_QWORD *)this + 56);
        v45[1] = v12;
        First = CCatalogTableSegmentIdIterator::FindFirst((CCatalogTableSegmentIdIterator *)v45);
        if ( First )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_85;
          }
          v15 = 206;
          goto LABEL_20;
        }
        First = CBaseRepubCacheTask::CheckIfCatalogRecordMarkedFree(
                  this,
                  *((struct _CatalogDatabaseDescriptor **)this + 51),
                  *((_QWORD *)this + 56));
        if ( First )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_85;
          }
          v15 = 207;
          goto LABEL_20;
        }
        v40 = 0;
        v41 = 0;
        v17 = *((_QWORD *)this + 52);
        LockSentry<ReadersWriterLock,1>::Attach(&v40, *(_QWORD *)(v17 + 72) + 112LL, v16);
        if ( v10 )
          memcpy_s(v10, v8, *(const void *const *)(*(_QWORD *)(v17 + 72) + 72LL), v8);
        LockSentry<ReadersWriterLock,1>::Unlock(&v40);
        if ( (_DWORD)v6 || v49 < v48 )
        {
          v20 = operator new[](Size);
          std::auto_ptr<unsigned short>::reset(&v42, v20);
          v11 = (char *)v42;
          v40 = v42;
          memset_0(v42, 0, Size);
          v21 = *(_DWORD *)(*((_QWORD *)this + 51) + 892LL);
          v22 = *((_QWORD *)this + 49);
          *(_OWORD *)v22 = 0;
          *(_OWORD *)(v22 + 16) = 0;
          *(_OWORD *)(v22 + 32) = 0;
          *(_DWORD *)v22 = v21;
          *(_DWORD *)(v22 + 16) = v48;
          *(_QWORD *)(v22 + 8) = v11;
          *(_DWORD *)(v22 + 32) = 1;
          v23 = *(_DWORD *)(*((_QWORD *)this + 51) + 888LL);
          v24 = *((_QWORD *)this + 49);
          *(_OWORD *)(v24 + 48) = 0;
          *(_OWORD *)(v24 + 64) = 0;
          *(_OWORD *)(v24 + 80) = 0;
          *(_DWORD *)(v24 + 48) = v23;
          v18 = v8;
          *(_DWORD *)(v24 + 64) = v8;
          *(_QWORD *)(v24 + 56) = v9;
          *(_DWORD *)(v24 + 80) = 1;
          Columns = JetRetrieveColumns(
                      *((_QWORD *)this + 47),
                      *((_QWORD *)this + 56),
                      *((JET_RETRIEVECOLUMN **)this + 49),
                      2u);
          if ( Columns )
          {
            First = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteHashesTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                      this,
                      Columns);
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_85;
            }
            v27 = 208;
            goto LABEL_49;
          }
          v47 = (unsigned int)v6;
          v28 = memcpy_s(&v11[(unsigned int)v6], Size, Source, SourceSize);
          if ( v28 )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 209, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v28);
            }
            First = 774;
            goto LABEL_85;
          }
        }
        else
        {
          v40 = Source;
          v47 = 0;
          v18 = v8;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
          {
            SourceSize = (rsize_t)v9;
            v39 = v18;
            WPP_SF__HEX_(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              210,
              WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
              &SourceSize);
            v19 = WPP_GLOBAL_Control;
          }
          if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v19 + 108) & 4) != 0
            && *((_BYTE *)v19 + 105) >= 3u )
          {
            SourceSize = (rsize_t)v10;
            v39 = v18;
            WPP_SF__HEX_(*((_QWORD *)v19 + 12), 211, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &SourceSize);
          }
        }
        First = CRepubCacheSegment::UpdateAvailableHashMask(
                  *((CRepubCacheSegment **)this + 52),
                  v47,
                  v49,
                  v8,
                  (unsigned __int8 *)v9,
                  (unsigned __int8 *)v10,
                  (bool *)this + 440);
        if ( First )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_85;
          }
          v15 = 212;
LABEL_20:
          WPP_SF_d(*((_QWORD *)v14 + 12), v15, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, First);
LABEL_85:
          v45[0] = &CBasePubCacheTableIterator::`vftable';
          operator delete(v11);
          operator delete(v10);
          operator delete(v9);
          return First;
        }
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
          {
            SourceSize = (rsize_t)v9;
            v39 = v8;
            WPP_SF__HEX_(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              213,
              WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
              &SourceSize);
            v29 = WPP_GLOBAL_Control;
          }
          if ( v29 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v29 + 108) & 4) != 0
            && *((_BYTE *)v29 + 105) >= 3u )
          {
            SourceSize = (rsize_t)v10;
            v39 = v8;
            WPP_SF__HEX_(*((_QWORD *)v29 + 12), 214, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &SourceSize);
          }
        }
        v30 = *(_DWORD *)(*((_QWORD *)this + 51) + 892LL);
        v31 = *((_QWORD *)this + 50);
        *(_DWORD *)(v31 + 4) = 0;
        *(_QWORD *)(v31 + 20) = 0;
        *(_QWORD *)(v31 + 32) = 0;
        *(_DWORD *)v31 = v30;
        *(_DWORD *)(v31 + 16) = v48;
        *(_QWORD *)(v31 + 8) = v40;
        *(_DWORD *)(v31 + 28) = 1;
        *(_DWORD *)(*((_QWORD *)this + 50) + 20LL) = 4;
        v32 = *(_DWORD *)(*((_QWORD *)this + 51) + 888LL);
        v33 = *((_QWORD *)this + 50);
        *(_DWORD *)(v33 + 44) = 0;
        *(_QWORD *)(v33 + 60) = 0;
        *(_QWORD *)(v33 + 72) = 0;
        *(_DWORD *)(v33 + 40) = v32;
        *(_DWORD *)(v33 + 56) = v8;
        *(_QWORD *)(v33 + 48) = v9;
        *(_DWORD *)(v33 + 68) = 1;
        v34 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 56), 2u);
        if ( v34 )
        {
          First = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteHashesTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                    this,
                    v34);
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_85;
          }
          v27 = 215;
        }
        else
        {
          v35 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 56), *((JET_SETCOLUMN **)this + 50), 2u);
          if ( v35 )
          {
            First = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteHashesTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                      this,
                      v35);
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_85;
            }
            v27 = 216;
          }
          else
          {
            v36 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 56), 0, 0, 0);
            if ( !v36 )
            {
              First = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 4) + 24LL))((char *)this + 32, 0);
              if ( !First )
              {
                CRepubCacheSegment::SetHashMaskAfterHashWrite(
                  *((CRepubCacheSegment **)this + 52),
                  v8,
                  (unsigned __int8 *)v9);
                *(_DWORD *)(*((_QWORD *)this + 54) + 56LL) = v49;
                goto LABEL_85;
              }
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                goto LABEL_85;
              }
              v15 = 218;
              goto LABEL_20;
            }
            First = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteHashesTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                      this,
                      v36);
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_85;
            }
            v27 = 217;
          }
        }
LABEL_49:
        WPP_SF_Dd(*((_QWORD *)v26 + 12), v27, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
        goto LABEL_85;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 204, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v6, v7, v4);
  }
  return 87;
}

```

## disassembly

```asm
0x1800863bc  push    rbp
0x1800863be  push    rbx
0x1800863bf  push    rsi
0x1800863c0  push    rdi
0x1800863c1  push    r12
0x1800863c3  push    r13
0x1800863c5  push    r14
0x1800863c7  push    r15
0x1800863c9  lea     rbp, [rsp-1Fh]
0x1800863ce  sub     rsp, 0B8h
0x1800863d5  mov     r14, rcx
0x1800863d8  lea     rdi, WPP_GLOBAL_Control
0x1800863df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800863e6  cmp     rcx, rdi
0x1800863e9  jz      short loc_180086413
0x1800863eb  test    byte ptr [rcx+6Ch], 4
0x1800863ef  jz      short loc_180086413
0x1800863f1  cmp     byte ptr [rcx+69h], 4
0x1800863f5  jb      short loc_180086413
0x1800863f7  mov     edx, 0CBh
0x1800863fc  mov     r9, [r14+1A0h]
0x180086403  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18008640a  mov     rcx, [rcx+60h]
0x18008640e  call    WPP_SF_q
0x180086413  mov     rcx, [r14+1A0h]
0x18008641a  add     rcx, 18h
0x18008641e  mov     rax, [rcx]
0x180086421  mov     rax, [rax+60h]
0x180086425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008642a  movzx   ebx, ax
0x18008642d  mov     word ptr [rbp+57h+arg_0], bx
0x180086431  mov     rcx, [r14+1A0h]
0x180086438  add     rcx, 18h
0x18008643c  mov     rdx, [rcx]
0x18008643f  mov     rax, [rdx+58h]
0x180086443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086448  mov     r8d, eax
0x18008644b  mov     [rbp+57h+arg_8], r8d
0x18008644f  mov     r9, [r14+1B0h]
0x180086456  mov     r13, [r9+48h]
0x18008645a  mov     r15d, [r9+3Ch]
0x18008645e  mov     [rbp+57h+arg_10], r15d
0x180086462  mov     eax, 0FFFFFFFFh
0x180086467  cmp     r13, rax
0x18008646a  ja      loc_180086BE9
0x180086470  mov     ecx, ebx
0x180086472  xor     edx, edx
0x180086474  mov     rax, r13
0x180086477  div     rbx
0x18008647a  test    rdx, rdx
0x18008647d  jnz     loc_180086BE9
0x180086483  mov     eax, r15d
0x180086486  div     ecx
0x180086488  test    edx, edx
0x18008648a  jnz     loc_180086BE9
0x180086490  mov     ecx, r8d
0x180086493  mov     [rbp+57h+Size], rcx
0x180086497  cmp     r13, r8
0x18008649a  ja      loc_180086BE9
0x1800864a0  cmp     r15d, r8d
0x1800864a3  ja      loc_180086BE9
0x1800864a9  mov     eax, r15d
0x1800864ac  mov     [rbp+57h+SourceSize], rax
0x1800864b0  add     rax, r13
0x1800864b3  cmp     rax, rcx
0x1800864b6  ja      loc_180086BE9
0x1800864bc  mov     rax, [r9+40h]
0x1800864c0  mov     [rbp+57h+Source], rax
0x1800864c4  mov     rcx, [r14+1A0h]
0x1800864cb  mov     rax, [rcx]
0x1800864ce  mov     rax, [rax+10h]
0x1800864d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864d7  add     eax, 7
0x1800864da  shr     eax, 3
0x1800864dd  mov     r12d, eax
0x1800864e0  mov     qword ptr [rbp+57h+arg_18], r12
0x1800864e4  mov     ecx, eax; unsigned __int64
0x1800864e6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800864eb  mov     rbx, rax
0x1800864ee  mov     [rbp+57h+var_58], rax
0x1800864f2  mov     r8d, r12d; Size
0x1800864f5  xor     edx, edx; Val
0x1800864f7  mov     rcx, rax; void *
0x1800864fa  call    memset_0
0x1800864ff  mov     ecx, r12d; unsigned __int64
0x180086502  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180086507  mov     rdi, rax
0x18008650a  mov     [rbp+57h+var_50], rax
0x18008650e  mov     r8d, r12d; Size
0x180086511  xor     edx, edx; Val
0x180086513  mov     rcx, rax; void *
0x180086516  call    memset_0
0x18008651b  xor     esi, esi
0x18008651d  mov     [rbp+57h+var_90], rsi
0x180086521  mov     rcx, cs:WPP_GLOBAL_Control
0x180086528  lea     rax, WPP_GLOBAL_Control
0x18008652f  cmp     rcx, rax
0x180086532  jz      short loc_18008656E
0x180086534  test    byte ptr [rcx+6Ch], 4
0x180086538  jz      short loc_18008656E
0x18008653a  cmp     byte ptr [rcx+69h], 4
0x18008653e  jb      short loc_18008656E
0x180086540  mov     edx, 0CDh
0x180086545  mov     eax, [rbp+57h+arg_8]
0x180086548  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18008654c  movzx   r8d, word ptr [rbp+57h+arg_0]
0x180086551  mov     dword ptr [rsp+0F0h+var_C8], r8d
0x180086556  mov     dword ptr [rsp+0F0h+pcbActual], r15d
0x18008655b  mov     r9, r13
0x18008655e  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180086565  mov     rcx, [rcx+60h]
0x180086569  call    WPP_SF_qDDD
0x18008656e  mov     rax, [r14+1A8h]
0x180086575  mov     rcx, [rax+18h]
0x180086579  lea     rax, ??_7CCatalogTableSegmentIdIterator@@6B@; const CCatalogTableSegmentIdIterator::`vftable'
0x180086580  mov     [rbp+57h+var_78], rax
0x180086584  mov     rax, [r14+178h]
0x18008658b  mov     [rbp+57h+var_68], rax
0x18008658f  mov     rax, [r14+1C0h]
0x180086596  mov     [rbp+57h+var_60], rax
0x18008659a  mov     [rbp+57h+var_70], rcx
0x18008659e  lea     rcx, [rbp+57h+var_78]; this
0x1800865a2  call    ?FindFirst@CCatalogTableSegmentIdIterator@@UEAAKXZ; CCatalogTableSegmentIdIterator::FindFirst(void)
0x1800865a7  mov     r15d, eax
0x1800865aa  test    eax, eax
0x1800865ac  jz      short loc_1800865FC
0x1800865ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800865b5  lea     rax, WPP_GLOBAL_Control
0x1800865bc  cmp     rcx, rax
0x1800865bf  jz      loc_180086BBF
0x1800865c5  test    byte ptr [rcx+6Ch], 4
0x1800865c9  jz      loc_180086BBF
0x1800865cf  mov     r12d, 1
0x1800865d5  cmp     [rcx+69h], r12b
0x1800865d9  jb      loc_180086BBF
0x1800865df  mov     edx, 0CEh
0x1800865e4  mov     r9d, r15d
0x1800865e7  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x1800865ee  mov     rcx, [rcx+60h]
0x1800865f2  call    WPP_SF_d
0x1800865f7  jmp     loc_180086BBF
0x1800865fc  mov     r8, [r14+1C0h]; unsigned __int64
0x180086603  mov     rdx, [r14+198h]; struct _CatalogDatabaseDescriptor *
0x18008660a  mov     rcx, r14; this
0x18008660d  call    ?CheckIfCatalogRecordMarkedFree@CBaseRepubCacheTask@@IEAAKPEAU_CatalogDatabaseDescriptor@@_K@Z; CBaseRepubCacheTask::CheckIfCatalogRecordMarkedFree(_CatalogDatabaseDescriptor *,unsigned __int64)
0x180086612  mov     r15d, eax
0x180086615  test    eax, eax
0x180086617  jz      short loc_180086651
0x180086619  mov     rcx, cs:WPP_GLOBAL_Control
0x180086620  lea     rax, WPP_GLOBAL_Control
0x180086627  cmp     rcx, rax
0x18008662a  jz      loc_180086BBF
0x180086630  test    byte ptr [rcx+6Ch], 4
0x180086634  jz      loc_180086BBF
0x18008663a  mov     r12d, 1
0x180086640  cmp     [rcx+69h], r12b
0x180086644  jb      loc_180086BBF
0x18008664a  mov     edx, 0CFh
0x18008664f  jmp     short loc_1800865E4
0x180086651  mov     [rbp+57h+var_A0], 0
0x180086659  mov     [rbp+57h+var_98], 0
0x18008665d  mov     r15, [r14+1A0h]
0x180086664  mov     rdx, [r15+48h]
0x180086668  add     rdx, 70h ; 'p'
0x18008666c  lea     rcx, [rbp+57h+var_A0]
0x180086670  call    ?Attach@?$LockSentry@VReadersWriterLock@@$00@@QEAAXAEAVReadersWriterLock@@_N@Z; LockSentry<ReadersWriterLock,1>::Attach(ReadersWriterLock &,bool)
0x180086675  test    rdi, rdi
0x180086678  jz      short loc_180086691
0x18008667a  mov     r8, [r15+48h]
0x18008667e  mov     r9, r12; SourceSize
0x180086681  mov     r8, [r8+48h]; Source
0x180086685  mov     rdx, r12; DestinationSize
0x180086688  mov     rcx, rdi; Destination
0x18008668b  call    cs:__imp_memcpy_s
0x180086691  lea     rcx, [rbp+57h+var_A0]
0x180086695  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$00@@QEAAXXZ; LockSentry<ReadersWriterLock,1>::Unlock(void)
0x18008669a  mov     r12d, 1
0x1800866a0  test    r13d, r13d
0x1800866a3  jnz     loc_1800867B4
0x1800866a9  mov     ecx, [rbp+57h+arg_10]
0x1800866ac  cmp     ecx, [rbp+57h+arg_8]
0x1800866af  jb      loc_1800867B4
0x1800866b5  mov     r8, [rbp+57h+Source]
0x1800866b9  mov     [rbp+57h+var_A0], r8
0x1800866bd  mov     eax, r13d
0x1800866c0  mov     [rbp+57h+arg_0], rax
0x1800866c4  mov     r15, qword ptr [rbp+57h+arg_18]
0x1800866c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800866cf  lea     r13, WPP_GLOBAL_Control
0x1800866d6  cmp     rcx, r13
0x1800866d9  jz      short loc_180086743
0x1800866db  test    byte ptr [rcx+6Ch], 4
0x1800866df  jz      short loc_180086710
0x1800866e1  cmp     byte ptr [rcx+69h], 3
0x1800866e5  jb      short loc_180086710
0x1800866e7  mov     [rbp+57h+SourceSize], rbx
0x1800866eb  mov     [rbp+57h+var_A8], r15w
0x1800866f0  mov     edx, 0D2h
0x1800866f5  lea     r9, [rbp+57h+SourceSize]
0x1800866f9  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180086700  mov     rcx, [rcx+60h]
0x180086704  call    WPP_SF__HEX_
0x180086709  mov     rcx, cs:WPP_GLOBAL_Control
0x180086710  cmp     rcx, r13
0x180086713  jz      short loc_180086743
0x180086715  test    byte ptr [rcx+6Ch], 4
0x180086719  jz      short loc_180086743
0x18008671b  cmp     byte ptr [rcx+69h], 3
0x18008671f  jb      short loc_180086743
0x180086721  mov     [rbp+57h+SourceSize], rdi
0x180086725  mov     [rbp+57h+var_A8], r15w
0x18008672a  mov     edx, 0D3h
0x18008672f  lea     r9, [rbp+57h+SourceSize]
0x180086733  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18008673a  mov     rcx, [rcx+60h]
0x18008673e  call    WPP_SF__HEX_
0x180086743  lea     rax, [r14+1B8h]
0x18008674a  mov     [rsp+0F0h+var_C0], rax; bool *
0x18008674f  mov     [rsp+0F0h+var_C8], rdi; unsigned __int8 *
0x180086754  mov     [rsp+0F0h+pcbActual], rbx; unsigned __int8 *
0x180086759  mov     r13, qword ptr [rbp+57h+arg_18]
0x18008675d  mov     r9d, r13d; unsigned int
0x180086760  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x180086764  mov     rdx, [rbp+57h+arg_0]; unsigned __int64
0x180086768  mov     rcx, [r14+1A0h]; this
0x18008676f  call    ?UpdateAvailableHashMask@CRepubCacheSegment@@QEAAK_KKKPEAE1PEA_N@Z; CRepubCacheSegment::UpdateAvailableHashMask(unsigned __int64,ulong,ulong,uchar *,uchar *,bool *)
0x180086774  mov     r15d, eax
0x180086777  test    eax, eax
0x180086779  jz      loc_180086935
0x18008677f  mov     rcx, cs:WPP_GLOBAL_Control
0x180086786  lea     rax, WPP_GLOBAL_Control
0x18008678d  cmp     rcx, rax
0x180086790  jz      loc_180086BBF
0x180086796  test    byte ptr [rcx+6Ch], 4
0x18008679a  jz      loc_180086BBF
0x1800867a0  cmp     [rcx+69h], r12b
0x1800867a4  jb      loc_180086BBF
0x1800867aa  mov     edx, 0D4h
0x1800867af  jmp     loc_1800865E4
0x1800867b4  mov     rcx, [rbp+57h+Size]; unsigned __int64
0x1800867b8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800867bd  mov     rdx, rax
0x1800867c0  lea     rcx, [rbp+57h+var_90]
0x1800867c4  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x1800867c9  mov     rsi, [rbp+57h+var_90]
0x1800867cd  mov     [rbp+57h+var_A0], rsi
0x1800867d1  mov     r8, [rbp+57h+Size]; Size
0x1800867d5  xor     edx, edx; Val
0x1800867d7  mov     rcx, rsi; void *
0x1800867da  call    memset_0
0x1800867df  mov     rax, [r14+198h]
0x1800867e6  mov     ecx, [rax+37Ch]
0x1800867ec  mov     rax, [r14+188h]
0x1800867f3  xorps   xmm0, xmm0
0x1800867f6  movups  xmmword ptr [rax], xmm0
0x1800867f9  movups  xmmword ptr [rax+10h], xmm0
0x1800867fd  movups  xmmword ptr [rax+20h], xmm0
0x180086801  mov     [rax], ecx
0x180086803  mov     ecx, [rbp+57h+arg_8]
0x180086806  mov     [rax+10h], ecx
0x180086809  mov     [rax+8], rsi
0x18008680d  mov     [rax+20h], r12d
0x180086811  mov     rax, [r14+198h]
0x180086818  mov     ecx, [rax+378h]
0x18008681e  mov     rax, [r14+188h]
0x180086825  movups  xmmword ptr [rax+30h], xmm0
0x180086829  movups  xmmword ptr [rax+40h], xmm0
0x18008682d  movups  xmmword ptr [rax+50h], xmm0
0x180086831  mov     [rax+30h], ecx
0x180086834  mov     r15, qword ptr [rbp+57h+arg_18]
0x180086838  mov     [rax+40h], r15d
0x18008683c  mov     [rax+38h], rbx
0x180086840  mov     [rax+50h], r12d
0x180086844  mov     r9d, 2; cretrievecolumn
0x18008684a  mov     r8, [r14+188h]; pretrievecolumn
0x180086851  mov     rdx, [r14+1C0h]; tableid
0x180086858  mov     rcx, [r14+178h]; sesid
0x18008685f  call    cs:__imp_JetRetrieveColumns
0x180086865  mov     edx, eax
0x180086867  mov     dword ptr [rbp+57h+arg_0], eax
0x18008686a  test    eax, eax
0x18008686c  jz      short loc_1800868CE
0x18008686e  mov     rcx, [r14]
0x180086871  mov     rax, [rcx+30h]
0x180086875  mov     rcx, r14
0x180086878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008687d  mov     r15d, eax
0x180086880  mov     rcx, cs:WPP_GLOBAL_Control
0x180086887  lea     rax, WPP_GLOBAL_Control
0x18008688e  cmp     rcx, rax
0x180086891  jz      loc_180086BBF
0x180086897  test    byte ptr [rcx+6Ch], 4
0x18008689b  jz      loc_180086BBF
0x1800868a1  cmp     [rcx+69h], r12b
0x1800868a5  jb      loc_180086BBF
0x1800868ab  mov     edx, 0D0h
0x1800868b0  mov     dword ptr [rsp+0F0h+pcbActual], r15d
0x1800868b5  mov     r9d, dword ptr [rbp+57h+arg_0]
0x1800868b9  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x1800868c0  mov     rcx, [rcx+60h]
  ... truncated ...
```
