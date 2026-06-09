# SetCostFlags(IBackgroundCopyJob *,ulong)

- ea: `0x18001e9f0`
- end: `0x18001eabd`
- name: `?SetCostFlags@@YAJPEAUIBackgroundCopyJob@@K@Z`
- size: `205`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b05c`

## callees

- `0x18000a2c0`
- `0x18001afb4`
- `0x18001e9f0`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetCostFlags(struct IBackgroundCopyJob *a1, int a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF

  v5 = 0;
  v3 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe,
         &v5);
  if ( v3 >= 0 )
  {
    v6 = 0;
    LODWORD(v6) = a2;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v5 + 424LL))(v5, 1, &v6);
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids, (unsigned int)v3);
  }
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001e9f0  mov     r11, rsp
0x18001e9f3  mov     [r11+8], rbx
0x18001e9f7  mov     [r11+10h], rsi
0x18001e9fb  push    rdi
0x18001e9fc  sub     rsp, 40h
0x18001ea00  mov     edi, edx
0x18001ea02  mov     qword ptr [r11-20h], 0
0x18001ea0a  lea     rsi, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001ea11  mov     [r11-28h], rsi
0x18001ea15  mov     rax, [rcx]
0x18001ea18  lea     r8, [r11-20h]
0x18001ea1c  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x18001ea23  mov     rax, [rax]
0x18001ea26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea2b  mov     ebx, eax
0x18001ea2d  test    eax, eax
0x18001ea2f  jns     short loc_18001EA64
0x18001ea31  lea     rax, WPP_GLOBAL_Control
0x18001ea38  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea3f  cmp     rcx, rax
0x18001ea42  jz      short loc_18001EA9B
0x18001ea44  test    byte ptr [rcx+1Ch], 4
0x18001ea48  jz      short loc_18001EA9B
0x18001ea4a  mov     edx, 15h
0x18001ea4f  mov     r9d, ebx
0x18001ea52  lea     r8, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids
0x18001ea59  mov     rcx, [rcx+10h]
0x18001ea5d  call    WPP_SF_d
0x18001ea62  jmp     short loc_18001EA9B
0x18001ea64  xorps   xmm0, xmm0
0x18001ea67  movups  [rsp+48h+var_18], xmm0
0x18001ea6c  mov     dword ptr [rsp+48h+var_18], edi
0x18001ea70  mov     rcx, [rsp+48h+var_20]
0x18001ea75  movaps  xmm0, [rsp+48h+var_18]
0x18001ea7a  movdqa  [rsp+48h+var_18], xmm0
0x18001ea80  mov     rax, [rcx]
0x18001ea83  lea     r8, [rsp+48h+var_18]
0x18001ea88  mov     edx, 1
0x18001ea8d  mov     rax, [rax+1A8h]
0x18001ea94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea99  mov     ebx, eax
0x18001ea9b  mov     [rsp+48h+var_28], rsi
0x18001eaa0  lea     rcx, [rsp+48h+var_20]
0x18001eaa5  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001eaaa  mov     eax, ebx
0x18001eaac  mov     rbx, [rsp+48h+arg_0]
0x18001eab1  mov     rsi, [rsp+48h+arg_8]
0x18001eab6  add     rsp, 40h
0x18001eaba  pop     rdi
0x18001eabb  retn
```
