# CSyncChangeWrapper::SetLocalRename(IAsynchronousNotifyingChangeApplierTarget *,unsigned __int64 *)

- ea: `0x18006d858`
- end: `0x18006d9c1`
- name: `?SetLocalRename@CSyncChangeWrapper@@QEAAJPEAUIAsynchronousNotifyingChangeApplierTarget@@PEA_K@Z`
- size: `361`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct IAsynchronousNotifyingChangeApplierTarget *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180033cec`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18006d858`
- `0x1800709c0`
- `0x180072e8c`
- `0x180094010`

## string_xrefs

- `0x18006d892`: `CSyncChangeWrapper::SetLocalRename`
- `0x18006d995`: `CSyncChangeWrapper::SetLocalRename`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::SetLocalRename(
        CSyncChangeWrapper *this,
        struct IAsynchronousNotifyingChangeApplierTarget *a2,
        unsigned __int64 *a3)
{
  PVOID *v6; // rcx
  int updated; // edi
  ULONGLONG *v8; // r14
  __int64 *v9; // rcx
  ULONGLONG v10; // rax
  __int64 v11; // rax
  unsigned int v12; // edx
  unsigned int *v13; // r9
  CSyncChangeUnitWrapper *v14; // rbx
  struct _SYNC_VERSION v16; // [rsp+30h] [rbp-48h] BYREF
  CSyncChangeUnitWrapper *v17; // [rsp+88h] [rbp+10h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      161,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::SetLocalRename");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  updated = -2147467261;
  if ( a2 && a3 )
  {
    v8 = (ULONGLONG *)((char *)this + 256);
    updated = (*(__int64 (__fastcall **)(struct IAsynchronousNotifyingChangeApplierTarget *, char *))(*(_QWORD *)a2 + 56LL))(
                a2,
                (char *)this + 256);
    if ( updated >= 0 )
    {
      v9 = (__int64 *)*((_QWORD *)this + 25);
      v10 = *v8;
      if ( v9 )
      {
        v16.ullTickCount = *v8;
        v11 = *v9;
        *(_QWORD *)&v16.dwLastUpdatingReplicaKey = 0;
        updated = (*(__int64 (__fastcall **)(__int64 *))(v11 + 40))(v9);
        if ( updated >= 0 )
        {
          v17 = 0;
          do
          {
            updated = CEnumSyncChangeUnitWrappers::Next(*((CEnumSyncChangeUnitWrappers **)this + 25), v12, &v17, v13);
            if ( updated )
              break;
            v14 = v17;
            updated = CSyncChangeUnitWrapper::SetUpdateVersion(v17, &v16);
            (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v14 + 16LL))(v14);
          }
          while ( updated >= 0 );
        }
      }
      else
      {
        *((_DWORD *)this + 28) = 0;
        *((_QWORD *)this + 15) = v10;
      }
      *a3 = *v8;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      162,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::SetLocalRename",
      updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18006d858  push    rbx
0x18006d85a  push    rsi
0x18006d85b  push    rdi
0x18006d85c  push    r12
0x18006d85e  push    r14
0x18006d860  push    r15
0x18006d862  sub     rsp, 48h
0x18006d866  mov     r15, r8
0x18006d869  mov     rbx, rdx
0x18006d86c  mov     rsi, rcx
0x18006d86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d876  lea     r12, WPP_GLOBAL_Control
0x18006d87d  cmp     rcx, r12
0x18006d880  jz      short loc_18006D8B1
0x18006d882  test    byte ptr [rcx+1Ch], 8
0x18006d886  jz      short loc_18006D8B1
0x18006d888  cmp     byte ptr [rcx+19h], 5
0x18006d88c  jb      short loc_18006D8B1
0x18006d88e  mov     rcx, [rcx+10h]
0x18006d892  lea     r9, aCsyncchangewra_73; "CSyncChangeWrapper::SetLocalRename"
0x18006d899  mov     edx, 0A1h
0x18006d89e  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006d8a5  call    WPP_SF_s
0x18006d8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d8b1  mov     edi, 80004003h
0x18006d8b6  test    rbx, rbx
0x18006d8b9  jz      loc_18006D980
0x18006d8bf  test    r15, r15
0x18006d8c2  jz      loc_18006D980
0x18006d8c8  mov     rax, [rbx]
0x18006d8cb  lea     r14, [rsi+100h]
0x18006d8d2  mov     rdx, r14
0x18006d8d5  mov     rcx, rbx
0x18006d8d8  mov     rax, [rax+38h]
0x18006d8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d8e1  mov     edi, eax
0x18006d8e3  test    eax, eax
0x18006d8e5  js      loc_18006D979
0x18006d8eb  mov     rcx, [rsi+0C8h]
0x18006d8f2  mov     rax, [r14]
0x18006d8f5  test    rcx, rcx
0x18006d8f8  jnz     short loc_18006D903
0x18006d8fa  mov     [rsi+70h], ecx
0x18006d8fd  mov     [rsi+78h], rax
0x18006d901  jmp     short loc_18006D973
0x18006d903  mov     [rsp+78h+var_48.ullTickCount], rax
0x18006d908  mov     rax, [rcx]
0x18006d90b  mov     qword ptr [rsp+78h+var_48.dwLastUpdatingReplicaKey], 0
0x18006d914  mov     rax, [rax+28h]
0x18006d918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d91d  mov     edi, eax
0x18006d91f  test    eax, eax
0x18006d921  js      short loc_18006D973
0x18006d923  mov     [rsp+78h+arg_8], 0
0x18006d92f  mov     rcx, [rsi+0C8h]; this
0x18006d936  lea     r8, [rsp+78h+arg_8]; struct CSyncChangeUnitWrapper **
0x18006d93e  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x18006d943  mov     edi, eax
0x18006d945  test    eax, eax
0x18006d947  jnz     short loc_18006D973
0x18006d949  mov     rbx, [rsp+78h+arg_8]
0x18006d951  lea     rdx, [rsp+78h+var_48]; struct _SYNC_VERSION *
0x18006d956  mov     rcx, rbx; this
0x18006d959  call    ?SetUpdateVersion@CSyncChangeUnitWrapper@@QEAAJPEAU_SYNC_VERSION@@@Z; CSyncChangeUnitWrapper::SetUpdateVersion(_SYNC_VERSION *)
0x18006d95e  mov     edi, eax
0x18006d960  mov     rcx, rbx
0x18006d963  mov     rax, [rbx]
0x18006d966  mov     rax, [rax+10h]
0x18006d96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d96f  test    edi, edi
0x18006d971  jns     short loc_18006D92F
0x18006d973  mov     rax, [r14]
0x18006d976  mov     [r15], rax
0x18006d979  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d980  cmp     rcx, r12
0x18006d983  jz      short loc_18006D9B1
0x18006d985  test    byte ptr [rcx+1Ch], 8
0x18006d989  jz      short loc_18006D9B1
0x18006d98b  cmp     byte ptr [rcx+19h], 5
0x18006d98f  jb      short loc_18006D9B1
0x18006d991  mov     rcx, [rcx+10h]
0x18006d995  lea     r9, aCsyncchangewra_73; "CSyncChangeWrapper::SetLocalRename"
0x18006d99c  mov     edx, 0A2h
0x18006d9a1  mov     [rsp+78h+var_58], edi
0x18006d9a5  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006d9ac  call    WPP_SF_sD
0x18006d9b1  mov     eax, edi
0x18006d9b3  add     rsp, 48h
0x18006d9b7  pop     r15
0x18006d9b9  pop     r14
0x18006d9bb  pop     r12
0x18006d9bd  pop     rdi
0x18006d9be  pop     rsi
0x18006d9bf  pop     rbx
0x18006d9c0  retn
```
