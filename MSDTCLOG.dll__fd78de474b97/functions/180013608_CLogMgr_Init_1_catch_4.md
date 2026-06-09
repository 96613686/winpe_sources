# _CLogMgr::Init_::_1_::catch$4

- ea: `0x180013608`
- end: `0x1800136a4`
- name: `_CLogMgr::Init_::_1_::catch$4`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d998`
- `0x180013608`
- `0x180015010`

## string_xrefs

- `0x180013677`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`

## pseudocode

```c
__int64 __fastcall CLogMgr::Init_::_1_::catch_4(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  int v5; // eax

  v3 = *(_QWORD *)(a2 + 256);
  v4 = *(_DWORD *)(a2 + 84);
  if ( *(_QWORD *)(v3 + 24) )
  {
    if ( v4 == -1073737662 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v3 + 24) + 24LL))(
             *(_QWORD *)(v3 + 24),
             4097,
             4);
      if ( v5 < 0 )
        TraceFile(v5, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 721);
    }
  }
  *(_DWORD *)(a2 + 288) = v4;
  return 0;
}

```

## disassembly

```asm
0x180013608  mov     [rsp+arg_8], rdx
0x18001360d  push    rbx
0x18001360e  push    rbp
0x18001360f  sub     rsp, 58h
0x180013613  mov     rbp, rdx
0x180013616  mov     rcx, [rbp+100h]
0x18001361d  mov     ebx, [rbp+54h]
0x180013620  cmp     qword ptr [rcx+18h], 0
0x180013625  jz      short loc_18001368C
0x180013627  cmp     ebx, 0C0001042h
0x18001362d  jnz     short loc_18001368C
0x18001362f  mov     rax, [rcx+18h]
0x180013633  mov     rdx, [rax]
0x180013636  mov     rax, [rdx+18h]
0x18001363a  mov     [rsp+68h+var_30], 0
0x180013643  mov     [rsp+68h+var_38], 0
0x18001364c  mov     [rsp+68h+var_40], 0
0x180013654  mov     [rsp+68h+var_48], ebx
0x180013658  xor     r9d, r9d
0x18001365b  mov     edx, 1001h
0x180013660  lea     r8d, [r9+4]
0x180013664  mov     rcx, [rcx+18h]
0x180013668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001366d  test    eax, eax
0x18001366f  jns     short loc_18001368C
0x180013671  mov     r9d, 2D1h; unsigned int
0x180013677  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18001367e  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x180013685  mov     ecx, eax; int
0x180013687  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18001368c  mov     [rbp+120h], ebx
0x180013692  mov     rax, 0
0x18001369c  add     rsp, 58h
0x1800136a0  pop     rbp
0x1800136a1  pop     rbx
0x1800136a2  retn
```
