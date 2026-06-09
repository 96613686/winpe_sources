# DllGetClassObject

- ea: `0x180002490`
- end: `0x1800025cf`
- name: `DllGetClassObject`
- size: `319`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x1800071ac`
- `0x180008bd4`
- `0x18000a010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002589`
- `KERNEL32!LeaveCriticalSection` at `0x180002589`
- `KERNEL32!EnterCriticalSection` at `0x18000255e`
- `KERNEL32!EnterCriticalSection` at `0x18000255e`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct CommonUtil::MpCoLibraryType **v6; // rdx
  CommonUtil *v7; // rcx
  void *v8; // r8
  unsigned int v9; // r9d
  HRESULT v10; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v12; // rsi
  _DWORD *v13; // rdx
  _QWORD *v14; // rdi
  char v16; // [rsp+58h] [rbp+20h] BYREF

  if ( !byte_180013731 )
  {
    byte_180013731 = 1;
    v16 = 0;
    if ( (int)CommonUtil::UtilIsHostedInExe((CommonUtil *)&v16, (unsigned __int16 **)riid, (unsigned __int16 *)ppv) >= 0 )
    {
      if ( v16 )
        CommonUtil::MpCoDontHandleExceptions(v7, v6, v8, v9);
    }
  }
  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v10 = 0;
  for ( i = off_180012150; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180012158; ++i )
  {
    v12 = *i;
    if ( *i )
    {
      if ( *((_QWORD *)v12 + 2) )
      {
        v13 = *(_DWORD **)v12;
        if ( rclsid->Data1 == **(_DWORD **)v12
          && *(_DWORD *)&rclsid->Data2 == v13[1]
          && *(_DWORD *)rclsid->Data4 == v13[2]
          && *(_DWORD *)&rclsid->Data4[4] == v13[3] )
        {
          v14 = (_QWORD *)((char *)v12 + 32);
          if ( !*((_QWORD *)v12 + 4) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v14 )
              v10 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v12 + 2))(
                      *((_QWORD *)v12 + 3),
                      &GUID_00000000_0000_0000_c000_000000000046,
                      (__int64)v12 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v14 )
            v10 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))*v14)(*v14, riid, ppv);
          break;
        }
      }
    }
  }
  if ( !*ppv && !v10 )
    return -2147221231;
  return v10;
}

```

## disassembly

```asm
0x180002490  mov     rax, rsp
0x180002493  mov     [rax+8], rbx
0x180002497  mov     [rax+10h], rbp
0x18000249b  push    rsi
0x18000249c  push    rdi
0x18000249d  push    r14
0x18000249f  sub     rsp, 20h
0x1800024a3  cmp     cs:byte_180013731, 0
0x1800024aa  mov     r14, r8
0x1800024ad  mov     rbp, rdx
0x1800024b0  mov     rdi, rcx
0x1800024b3  jnz     short loc_1800024D9
0x1800024b5  lea     rcx, [rax+20h]; this
0x1800024b9  mov     cs:byte_180013731, 1
0x1800024c0  mov     byte ptr [rax+20h], 0
0x1800024c4  call    ?UtilIsHostedInExe@CommonUtil@@YAJPEA_NPEBG@Z; CommonUtil::UtilIsHostedInExe(bool *,ushort const *)
0x1800024c9  test    eax, eax
0x1800024cb  js      short loc_1800024D9
0x1800024cd  cmp     [rsp+38h+arg_18], 0
0x1800024d2  jz      short loc_1800024D9
0x1800024d4  call    ?MpCoDontHandleExceptions@CommonUtil@@YAJXZ; CommonUtil::MpCoDontHandleExceptions(void)
0x1800024d9  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800024e0  jnz     short loc_1800024EC
0x1800024e2  mov     ebx, 8000FFFFh
0x1800024e7  jmp     loc_1800025BA
0x1800024ec  test    r14, r14
0x1800024ef  jnz     short loc_1800024FB
0x1800024f1  mov     ebx, 80004003h
0x1800024f6  jmp     loc_1800025BA
0x1800024fb  mov     qword ptr [r14], 0
0x180002502  xor     ebx, ebx
0x180002504  mov     rcx, cs:off_180012150
0x18000250b  mov     r8, cs:off_180012158
0x180002512  jmp     short loc_180002547
0x180002514  mov     rsi, [rcx]
0x180002517  test    rsi, rsi
0x18000251a  jz      short loc_180002543
0x18000251c  cmp     [rsi+10h], rbx
0x180002520  jz      short loc_180002543
0x180002522  mov     rdx, [rsi]
0x180002525  mov     eax, [rdx]
0x180002527  cmp     [rdi], eax
0x180002529  jnz     short loc_180002543
0x18000252b  mov     eax, [rdx+4]
0x18000252e  cmp     [rdi+4], eax
0x180002531  jnz     short loc_180002543
0x180002533  mov     eax, [rdx+8]
0x180002536  cmp     [rdi+8], eax
0x180002539  jnz     short loc_180002543
0x18000253b  mov     eax, [rdx+0Ch]
0x18000253e  cmp     [rdi+0Ch], eax
0x180002541  jz      short loc_18000254E
0x180002543  add     rcx, 8
0x180002547  cmp     rcx, r8
0x18000254a  jb      short loc_180002514
0x18000254c  jmp     short loc_1800025AA
0x18000254e  lea     rdi, [rsi+20h]
0x180002552  cmp     [rdi], rbx
0x180002555  jnz     short loc_18000258F
0x180002557  lea     rcx, CriticalSection; lpCriticalSection
0x18000255e  call    cs:__imp_EnterCriticalSection
0x180002564  cmp     [rdi], rbx
0x180002567  jnz     short loc_180002582
0x180002569  mov     rcx, [rsi+18h]
0x18000256d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002574  mov     rax, [rsi+10h]
0x180002578  mov     r8, rdi
0x18000257b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002580  mov     ebx, eax
0x180002582  lea     rcx, CriticalSection; lpCriticalSection
0x180002589  call    cs:__imp_LeaveCriticalSection
0x18000258f  mov     rcx, [rdi]
0x180002592  test    rcx, rcx
0x180002595  jz      short loc_1800025AA
0x180002597  mov     rax, [rcx]
0x18000259a  mov     r8, r14
0x18000259d  mov     rdx, rbp
0x1800025a0  mov     rax, [rax]
0x1800025a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025a8  mov     ebx, eax
0x1800025aa  cmp     qword ptr [r14], 0
0x1800025ae  jnz     short loc_1800025BA
0x1800025b0  test    ebx, ebx
0x1800025b2  mov     eax, 80040111h
0x1800025b7  cmovz   ebx, eax
0x1800025ba  mov     rbp, [rsp+38h+arg_8]
0x1800025bf  mov     eax, ebx
0x1800025c1  mov     rbx, [rsp+38h+arg_0]
0x1800025c6  add     rsp, 20h
0x1800025ca  pop     r14
0x1800025cc  pop     rdi
0x1800025cd  pop     rsi
0x1800025ce  retn
```
