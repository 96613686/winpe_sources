# Broker::BackgroundTaskCapabilityWrapper::CheckCapability(ushort const *,void *,ulong)

- ea: `0x1800147bc`
- end: `0x18001486d`
- name: `?CheckCapability@BackgroundTaskCapabilityWrapper@Broker@@QEAA_NPEBGPEAXK@Z`
- size: `177`
- prototype: `bool __fastcall(Broker::BackgroundTaskCapabilityWrapper *__hidden this, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800110a0`

## callees

- `0x1800147bc`
- `0x1800165da`
- `0x18001a070`
- `0x18001e010`

## pseudocode

```c
bool __fastcall Broker::BackgroundTaskCapabilityWrapper::CheckCapability(
        Broker::BackgroundTaskCapabilityWrapper *this,
        const unsigned __int16 *a2,
        void *a3,
        unsigned int a4)
{
  __int64 v4; // rcx
  int v6; // eax
  unsigned __int16 v7; // bx
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+38h] [rbp-30h]
  int v11; // [rsp+48h] [rbp-20h]
  int v12; // [rsp+50h] [rbp-18h]
  int v13; // [rsp+70h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  v13 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, void *, _QWORD, int *))(*(_QWORD *)v4 + 56LL))(
         v4,
         a2,
         a3,
         a4,
         &v13);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, a4, v6);
    v11 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v12 = v7;
    v10 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  return v13 != 0;
}

```

## disassembly

```asm
0x1800147bc  mov     [rsp+arg_8], rbx
0x1800147c1  push    rdi
0x1800147c2  sub     rsp, 60h
0x1800147c6  mov     rcx, [rcx]
0x1800147c9  mov     edi, r9d
0x1800147cc  lea     r9, [rsp+68h+arg_0]
0x1800147d1  mov     [rsp+68h+arg_0], 0
0x1800147d9  mov     [rsp+68h+var_48], r9
0x1800147de  mov     r9d, edi
0x1800147e1  mov     rax, [rcx]
0x1800147e4  mov     rax, [rax+38h]
0x1800147e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ed  mov     ebx, eax
0x1800147ef  test    eax, eax
0x1800147f1  jns     short loc_18001485A
0x1800147f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147fa  test    dword ptr [rcx+1Ch], 400h
0x180014801  jz      short loc_180014825
0x180014803  cmp     byte ptr [rcx+19h], 2
0x180014807  jb      short loc_180014825
0x180014809  mov     rcx, [rcx+10h]
0x18001480d  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180014814  mov     edx, 11h
0x180014819  mov     dword ptr [rsp+68h+var_48], eax
0x18001481d  mov     r9d, edi
0x180014820  call    WPP_SF_dd
0x180014825  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001482c  mov     [rsp+68h+var_20], 1
0x180014834  mov     [rsp+68h+pExceptionObject], rax
0x180014839  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180014840  movzx   eax, bx
0x180014843  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180014848  xorps   xmm0, xmm0
0x18001484b  mov     [rsp+68h+var_18], eax
0x18001484f  movups  [rsp+68h+var_30], xmm0
0x180014854  call    _CxxThrowException_0
0x18001485a  cmp     [rsp+68h+arg_0], 0
0x18001485f  mov     rbx, [rsp+68h+arg_8]
0x180014864  setnz   al
0x180014867  add     rsp, 60h
0x18001486b  pop     rdi
0x18001486c  retn
```
