# CAutoInitCopyAccelerator::~CAutoInitCopyAccelerator(void)

- ea: `0x14001d330`
- end: `0x14001d414`
- name: `??1CAutoInitCopyAccelerator@@QEAA@XZ`
- size: `228`
- prototype: `void __fastcall(CAutoInitCopyAccelerator *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x14001dba4`
- `0x140026270`

## callees

- `0x1400029a8`
- `0x140005c40`
- `0x14001d330`
- `0x14001da70`
- `0x14001e350`
- `0x140024148`
- `0x1400244c4`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x14001d3c5`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001d3f4`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001d3c5`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001d3f4`
- `KERNEL32!LocalFree` at `0x14001d3dc`
- `KERNEL32!LocalFree` at `0x14001d3dc`

## string_xrefs

- `0x14001d362`: `CleanupCopyAcceleratorRpc failed. hr = %#lx\n`

## pseudocode

```c
void __fastcall CAutoInitCopyAccelerator::~CAutoInitCopyAccelerator(CAutoInitCopyAccelerator *this)
{
  int v2; // eax
  unsigned int v3; // edi
  void *v4; // rcx
  unsigned __int64 v5; // rdx
  void *v6; // rcx

  if ( (*(_BYTE *)this & 1) != 0 )
  {
    if ( (*(_BYTE *)this & 4) != 0 )
    {
      v2 = CopyAcceleratorRpc::Cleanup((CAutoInitCopyAccelerator *)((char *)this + 8));
      v3 = v2;
      if ( v2 < 0 )
      {
        if ( (*(_BYTE *)this & 2) != 0 )
          MpCmdLogPrintf(L"CleanupCopyAcceleratorRpc failed. hr = %#lx\n", (unsigned int)v2);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids, v3);
      }
    }
    if ( (*(_BYTE *)this & 2) != 0 )
      UninitializeLog();
    CleanupMpAsimov();
    *(_QWORD *)this = 0;
  }
  if ( *((_QWORD *)this + 4) )
  {
    MpConfigUnregisterNotifications();
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
    LocalFree(v4);
  CopyAcceleratorRpc::Cleanup((CAutoInitCopyAccelerator *)((char *)this + 8));
  if ( *((_QWORD *)this + 4) )
    MpConfigUnregisterNotifications();
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    operator delete(v6, v5);
}

```

## disassembly

```asm
0x14001d330  mov     [rsp+arg_8], rbx
0x14001d335  mov     [rsp+arg_0], rcx
0x14001d33a  push    rdi
0x14001d33b  sub     rsp, 20h
0x14001d33f  mov     rbx, rcx
0x14001d342  test    byte ptr [rcx], 1
0x14001d345  jz      short loc_14001D3B5
0x14001d347  test    byte ptr [rcx], 4
0x14001d34a  jz      short loc_14001D39F
0x14001d34c  add     rcx, 8; this
0x14001d350  call    ?Cleanup@CopyAcceleratorRpc@@QEAAJXZ; CopyAcceleratorRpc::Cleanup(void)
0x14001d355  mov     edi, eax
0x14001d357  test    eax, eax
0x14001d359  jns     short loc_14001D39F
0x14001d35b  test    byte ptr [rbx], 2
0x14001d35e  jz      short loc_14001D36E
0x14001d360  mov     edx, eax
0x14001d362  lea     rcx, aCleanupcopyacc; "CleanupCopyAcceleratorRpc failed. hr = "...
0x14001d369  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001d36e  lea     rax, WPP_GLOBAL_Control
0x14001d375  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d37c  cmp     rcx, rax
0x14001d37f  jz      short loc_14001D39F
0x14001d381  test    byte ptr [rcx+1Ch], 1
0x14001d385  jz      short loc_14001D39F
0x14001d387  mov     edx, 0Dh
0x14001d38c  mov     r9d, edi
0x14001d38f  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001d396  mov     rcx, [rcx+10h]
0x14001d39a  call    WPP_SF_d
0x14001d39f  test    byte ptr [rbx], 2
0x14001d3a2  jz      short loc_14001D3A9
0x14001d3a4  call    ?UninitializeLog@@YAXXZ; UninitializeLog(void)
0x14001d3a9  call    ?CleanupMpAsimov@@YAXXZ; CleanupMpAsimov(void)
0x14001d3ae  mov     qword ptr [rbx], 0
0x14001d3b5  jmp     short loc_14001D3BC
0x14001d3b7  mov     rbx, [rsp+28h+arg_0]
0x14001d3bc  mov     rcx, [rbx+20h]
0x14001d3c0  test    rcx, rcx
0x14001d3c3  jz      short loc_14001D3D3
0x14001d3c5  call    cs:__imp_MpConfigUnregisterNotifications
0x14001d3cb  mov     qword ptr [rbx+20h], 0
0x14001d3d3  mov     rcx, [rbx+10h]; hMem
0x14001d3d7  test    rcx, rcx
0x14001d3da  jz      short loc_14001D3E2
0x14001d3dc  call    cs:__imp_LocalFree
0x14001d3e2  lea     rcx, [rbx+8]; this
0x14001d3e6  call    ?Cleanup@CopyAcceleratorRpc@@QEAAJXZ; CopyAcceleratorRpc::Cleanup(void)
0x14001d3eb  mov     rcx, [rbx+20h]
0x14001d3ef  test    rcx, rcx
0x14001d3f2  jz      short loc_14001D3FA
0x14001d3f4  call    cs:__imp_MpConfigUnregisterNotifications
0x14001d3fa  mov     rcx, [rbx+8]; void *
0x14001d3fe  test    rcx, rcx
0x14001d401  jz      short loc_14001D409
0x14001d403  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d408  nop
0x14001d409  mov     rbx, [rsp+28h+arg_8]
0x14001d40e  add     rsp, 20h
0x14001d412  pop     rdi
0x14001d413  retn
```
