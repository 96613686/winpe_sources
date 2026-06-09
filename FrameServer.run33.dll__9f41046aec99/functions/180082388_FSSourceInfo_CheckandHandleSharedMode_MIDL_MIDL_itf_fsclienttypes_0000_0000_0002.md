# FSSourceInfo::CheckandHandleSharedMode(__MIDL___MIDL_itf_fsclienttypes_0000_0000_0002)

- ea: `0x180082388`
- end: `0x1800824da`
- name: `?CheckandHandleSharedMode@FSSourceInfo@@QEAAJW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0002@@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800726a0`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x18006b99c`
- `0x180082388`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800824c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800824c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008239a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008239a`
- `MFPlat!MFCreateMediaEvent` at `0x18008242a`
- `MFPlat!MFCreateMediaEvent` at `0x18008242a`

## pseudocode

```c
__int64 __fastcall FSSourceInfo::CheckandHandleSharedMode(__int64 a1, int a2)
{
  unsigned int v4; // edi
  HRESULT v5; // eax
  IMFMediaEvent *ppEvent; // [rsp+60h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( *(_QWORD *)(a1 + 96) )
  {
    v4 = 0;
    if ( a2 == 1 && !(unsigned int)FSSourceInfo::GetShareMode(a1) && *(_BYTE *)(a1 + 208) )
    {
      ppEvent = 0;
      if ( byte_18010EC4D )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 83, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
      v5 = MFCreateMediaEvent(0x320u, &GUID_00000000_0000_0000_0000_000000000000, -1072873822, 0, &ppEvent);
      v4 = v5;
      if ( v5 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, IMFMediaEvent *, __int64))(**(_QWORD **)(a1 + 96) + 264LL))(
               *(_QWORD *)(a1 + 96),
               -1,
               ppEvent,
               1);
      }
      else if ( g_wppLevels )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v5);
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppEvent);
    }
  }
  else
  {
    v4 = -1072873851;
    if ( g_wppLevels >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
        a1,
        -1072873851);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  return v4;
}

```

## disassembly

```asm
0x180082388  push    rbx
0x18008238a  push    rbp
0x18008238b  push    rsi
0x18008238c  push    rdi
0x18008238d  sub     rsp, 38h
0x180082391  mov     rbx, rcx
0x180082394  mov     ebp, edx
0x180082396  add     rcx, 10h; lpCriticalSection
0x18008239a  call    cs:__imp_EnterCriticalSection
0x1800823a0  cmp     qword ptr [rbx+60h], 0
0x1800823a5  jz      loc_180082494
0x1800823ab  xor     edi, edi
0x1800823ad  cmp     ebp, 1
0x1800823b0  jnz     loc_1800824C5
0x1800823b6  mov     rcx, rbx
0x1800823b9  call    ?GetShareMode@FSSourceInfo@@QEBA?AW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@XZ; FSSourceInfo::GetShareMode(void)
0x1800823be  test    eax, eax
0x1800823c0  jnz     loc_1800824C5
0x1800823c6  cmp     [rbx+0D0h], dil
0x1800823cd  jz      loc_1800824C5
0x1800823d3  mov     [rsp+58h+arg_0], rdi
0x1800823d8  cmp     cs:byte_18010EC4D, bpl
0x1800823df  jb      short loc_180082401
0x1800823e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800823e8  lea     edx, [rdi+53h]
0x1800823eb  mov     r9, rbx
0x1800823ee  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x1800823f5  mov     rcx, [rcx+0D8h]
0x1800823fc  call    WPP_SF_q
0x180082401  lea     rcx, [rsp+58h+arg_0]
0x180082406  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008240b  lea     rax, [rsp+58h+arg_0]
0x180082410  xor     r9d, r9d; pvValue
0x180082413  mov     r8d, 0C00D3EA2h; hrStatus
0x180082419  mov     [rsp+58h+ppEvent], rax; ppEvent
0x18008241e  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x180082425  mov     ecx, 320h; met
0x18008242a  call    cs:__imp_MFCreateMediaEvent
0x180082430  mov     edi, eax
0x180082432  test    eax, eax
0x180082434  jns     short loc_18008246E
0x180082436  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008243d  jb      short loc_180082462
0x18008243f  mov     rcx, cs:WPP_GLOBAL_Control
0x180082446  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x18008244d  mov     edx, 54h ; 'T'
0x180082452  mov     dword ptr [rsp+58h+ppEvent], eax
0x180082456  mov     r9, rbx
0x180082459  mov     rcx, [rcx+10h]
0x18008245d  call    WPP_SF_qD
0x180082462  lea     rcx, [rsp+58h+arg_0]; void *
0x180082467  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18008246c  jmp     short loc_1800824C5
0x18008246e  mov     rcx, [rbx+60h]
0x180082472  mov     r9d, 1
0x180082478  mov     r8, [rsp+58h+arg_0]
0x18008247d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180082481  mov     rax, [rcx]
0x180082484  mov     rax, [rax+108h]
0x18008248b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082490  mov     edi, eax
0x180082492  jmp     short loc_180082462
0x180082494  mov     edi, 0C00D3E85h
0x180082499  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800824a0  jb      short loc_1800824C5
0x1800824a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824a9  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x1800824b0  mov     edx, 52h ; 'R'
0x1800824b5  mov     dword ptr [rsp+58h+ppEvent], edi
0x1800824b9  mov     r9, rbx
0x1800824bc  mov     rcx, [rcx+10h]
0x1800824c0  call    WPP_SF_qD
0x1800824c5  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800824c9  call    cs:__imp_LeaveCriticalSection
0x1800824cf  mov     eax, edi
0x1800824d1  add     rsp, 38h
0x1800824d5  pop     rdi
0x1800824d6  pop     rsi
0x1800824d7  pop     rbp
0x1800824d8  pop     rbx
0x1800824d9  retn
```
