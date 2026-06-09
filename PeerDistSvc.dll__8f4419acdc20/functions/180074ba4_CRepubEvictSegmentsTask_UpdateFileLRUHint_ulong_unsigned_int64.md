# CRepubEvictSegmentsTask::UpdateFileLRUHint(ulong,unsigned __int64)

- ea: `0x180074ba4`
- end: `0x180074d42`
- name: `?UpdateFileLRUHint@CRepubEvictSegmentsTask@@IEAAKK_K@Z`
- size: `414`
- prototype: `unsigned int __fastcall(CRepubEvictSegmentsTask *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18006ea00`
- `0x18006ed80`
- `0x180075220`

## callees

- `0x180008290`
- `0x180074ba4`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180074c20`
- `ESENT!JetPrepareUpdate` at `0x180074c20`
- `ESENT!JetSetColumns` at `0x180074c88`
- `ESENT!JetSetColumns` at `0x180074c88`
- `ESENT!JetUpdate` at `0x180074cd8`
- `ESENT!JetUpdate` at `0x180074cd8`

## pseudocode

```c
__int64 __fastcall CRepubEvictSegmentsTask::UpdateFileLRUHint(
        CRepubEvictSegmentsTask *this,
        unsigned int a2,
        __int64 a3)
{
  __int64 v4; // rsi
  int v5; // r8d
  __int64 v6; // rax
  unsigned int v7; // edi
  CHostedCacheMsgEncoding *v8; // r10
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v11; // edi
  unsigned int v12; // eax
  unsigned int v13; // esi
  __int64 v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = a3;
  v4 = a2;
  v5 = *(_DWORD *)(768LL * a2 + *((_QWORD *)this + 52) + 636);
  v6 = *((_QWORD *)this + 50);
  *(_DWORD *)(v6 + 4) = 0;
  *(_QWORD *)(v6 + 20) = 0;
  *(_QWORD *)(v6 + 32) = 0;
  *(_DWORD *)v6 = v5;
  *(_DWORD *)(v6 + 16) = 8;
  *(_QWORD *)(v6 + 8) = &v15;
  *(_DWORD *)(v6 + 28) = 1;
  v7 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + a2 + 67), 2u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_7;
    }
    v9 = 311;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v8 + 12), v9, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v7);
LABEL_7:
    v10 = v7;
    return (*(unsigned int (__fastcall **)(CRepubEvictSegmentsTask *, __int64))(*(_QWORD *)this + 48LL))(this, v10);
  }
  v7 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + v4 + 67), *((JET_SETCOLUMN **)this + 50), 1u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_7;
    }
    v9 = 312;
    goto LABEL_6;
  }
  v11 = 0;
  v12 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + v4 + 67), 0, 0, 0);
  v13 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 313, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v12);
    }
    v10 = v13;
    return (*(unsigned int (__fastcall **)(CRepubEvictSegmentsTask *, __int64))(*(_QWORD *)this + 48LL))(this, v10);
  }
  return v11;
}

```

## disassembly

```asm
0x180074ba4  mov     r11, rsp
0x180074ba7  mov     [r11+8], rbx
0x180074bab  mov     [r11+10h], rsi
0x180074baf  mov     [r11+18h], r8
0x180074bb3  push    rdi
0x180074bb4  sub     rsp, 30h
0x180074bb8  mov     rax, [rcx+1A0h]
0x180074bbf  mov     rbx, rcx
0x180074bc2  mov     esi, edx
0x180074bc4  lea     rdx, [rsi+rsi*2]
0x180074bc8  shl     rdx, 8
0x180074bcc  mov     r8d, [rdx+rax+27Ch]
0x180074bd4  mov     rax, [rcx+190h]
0x180074bdb  lea     rcx, [r11+18h]
0x180074bdf  mov     dword ptr [rax+4], 0
0x180074be6  mov     qword ptr [rax+14h], 0
0x180074bee  mov     qword ptr [rax+20h], 0
0x180074bf6  mov     [rax], r8d
0x180074bf9  mov     r8d, 2; prep
0x180074bff  mov     dword ptr [rax+10h], 8
0x180074c06  mov     [rax+8], rcx
0x180074c0a  mov     dword ptr [rax+1Ch], 1
0x180074c11  mov     rdx, [rbx+rsi*8+218h]; tableid
0x180074c19  mov     rcx, [rbx+178h]; sesid
0x180074c20  call    cs:__imp_JetPrepareUpdate
0x180074c26  mov     edi, eax
0x180074c28  test    eax, eax
0x180074c2a  jz      short loc_180074C6C
0x180074c2c  mov     r10, cs:WPP_GLOBAL_Control
0x180074c33  lea     rcx, WPP_GLOBAL_Control
0x180074c3a  cmp     r10, rcx
0x180074c3d  jz      short loc_180074C65
0x180074c3f  test    byte ptr [r10+6Ch], 4
0x180074c44  jz      short loc_180074C65
0x180074c46  cmp     byte ptr [r10+69h], 1
0x180074c4b  jb      short loc_180074C65
0x180074c4d  mov     edx, 137h
0x180074c52  mov     rcx, [r10+60h]
0x180074c56  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180074c5d  mov     r9d, edi
0x180074c60  call    WPP_SF_d
0x180074c65  mov     edx, edi
0x180074c67  jmp     loc_180074D1F
0x180074c6c  mov     r8, [rbx+190h]; psetcolumn
0x180074c73  mov     r9d, 1; csetcolumn
0x180074c79  mov     rdx, [rbx+rsi*8+218h]; tableid
0x180074c81  mov     rcx, [rbx+178h]; sesid
0x180074c88  call    cs:__imp_JetSetColumns
0x180074c8e  mov     edi, eax
0x180074c90  test    eax, eax
0x180074c92  jz      short loc_180074CBC
0x180074c94  mov     r10, cs:WPP_GLOBAL_Control
0x180074c9b  lea     rcx, WPP_GLOBAL_Control
0x180074ca2  cmp     r10, rcx
0x180074ca5  jz      short loc_180074C65
0x180074ca7  test    byte ptr [r10+6Ch], 4
0x180074cac  jz      short loc_180074C65
0x180074cae  cmp     byte ptr [r10+69h], 1
0x180074cb3  jb      short loc_180074C65
0x180074cb5  mov     edx, 138h
0x180074cba  jmp     short loc_180074C52
0x180074cbc  mov     rdx, [rbx+rsi*8+218h]; tableid
0x180074cc4  xor     edi, edi
0x180074cc6  mov     rcx, [rbx+178h]; sesid
0x180074ccd  xor     r9d, r9d; cbBookmark
0x180074cd0  xor     r8d, r8d; pvBookmark
0x180074cd3  mov     [rsp+38h+pcbActual], rdi; pcbActual
0x180074cd8  call    cs:__imp_JetUpdate
0x180074cde  mov     esi, eax
0x180074ce0  test    eax, eax
0x180074ce2  jz      short loc_180074D30
0x180074ce4  mov     r10, cs:WPP_GLOBAL_Control
0x180074ceb  lea     rcx, WPP_GLOBAL_Control
0x180074cf2  cmp     r10, rcx
0x180074cf5  jz      short loc_180074D1D
0x180074cf7  test    byte ptr [r10+6Ch], 4
0x180074cfc  jz      short loc_180074D1D
0x180074cfe  cmp     byte ptr [r10+69h], 1
0x180074d03  jb      short loc_180074D1D
0x180074d05  mov     rcx, [r10+60h]
0x180074d09  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180074d10  mov     edx, 139h
0x180074d15  mov     r9d, eax
0x180074d18  call    WPP_SF_d
0x180074d1d  mov     edx, esi
0x180074d1f  mov     rax, [rbx]
0x180074d22  mov     rcx, rbx
0x180074d25  mov     rax, [rax+30h]
0x180074d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074d2e  mov     edi, eax
0x180074d30  mov     rbx, [rsp+38h+arg_0]
0x180074d35  mov     eax, edi
0x180074d37  mov     rsi, [rsp+38h+arg_8]
0x180074d3c  add     rsp, 30h
0x180074d40  pop     rdi
0x180074d41  retn
```
