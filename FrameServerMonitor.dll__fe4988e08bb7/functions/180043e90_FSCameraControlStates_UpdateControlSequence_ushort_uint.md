# FSCameraControlStates::UpdateControlSequence(ushort,uint)

- ea: `0x180043e90`
- end: `0x180044013`
- name: `?UpdateControlSequence@FSCameraControlStates@@UEAAJGI@Z`
- size: `387`
- prototype: `int(FSCameraControlStates *__hidden this, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005f98`
- `0x180006a98`
- `0x180007348`
- `0x180043e90`
- `0x18004401c`
- `0x1800447f0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043eaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043eaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043ffa`
- `MFPlat!MFGetSystemTime` at `0x180043fbb`
- `MFPlat!MFGetSystemTime` at `0x180043fbb`

## pseudocode

```c
__int64 __fastcall FSCameraControlStates::UpdateControlSequence(
        FSCameraControlStates *this,
        unsigned __int16 a2,
        unsigned int a3)
{
  unsigned int v6; // r12d
  _QWORD *v7; // r14
  __int64 v8; // rdi
  __int64 v9; // r13
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // rdx
  struct IFSCameraControlState *v15; // [rsp+90h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v6 = *((_DWORD *)this + 16);
  v7 = (_QWORD *)((char *)this + 56);
  v8 = 0;
  if ( v6 )
  {
    while ( 1 )
    {
      v9 = (unsigned int)v8;
      if ( (*(unsigned __int16 (__fastcall **)(_QWORD))(**(_QWORD **)(*v7 + 8 * v8) + 24LL))(*(_QWORD *)(*v7 + 8 * v8)) == a2
        && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*v7 + 8 * v8) + 32LL))(*(_QWORD *)(*v7 + 8 * v8)) == a3 )
      {
        break;
      }
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= v6 )
        goto LABEL_5;
    }
    v11 = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*v7 + 8 * v9) + 48LL))(*(_QWORD *)(*v7 + 8 * v9));
LABEL_15:
    *((_QWORD *)this + 15) = MFGetSystemTime();
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v13 = 26;
      goto LABEL_17;
    }
    goto LABEL_18;
  }
LABEL_5:
  v15 = 0;
  v10 = FSCameraControlState::CreateCameraControlState(a2, a3, &v15);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( (unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)this + 7, (__int64)v15) )
    {
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v15);
      goto LABEL_15;
    }
    v11 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids,
        this,
        -2147024882);
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids, this, v10);
  }
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v15);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v13 = 27;
LABEL_17:
    WPP_SF_qDsDD(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v12, this, v11);
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v11;
}

```

## disassembly

```asm
0x180043e90  push    rbx
0x180043e92  push    rbp
0x180043e93  push    rsi
0x180043e94  push    rdi
0x180043e95  push    r12
0x180043e97  push    r13
0x180043e99  push    r14
0x180043e9b  push    r15
0x180043e9d  sub     rsp, 48h
0x180043ea1  mov     rsi, rcx
0x180043ea4  movzx   r15d, dx
0x180043ea8  add     rcx, 8; lpCriticalSection
0x180043eac  mov     ebp, r8d
0x180043eaf  call    cs:__imp_EnterCriticalSection
0x180043eb5  mov     r12d, [rsi+40h]
0x180043eb9  lea     r14, [rsi+38h]
0x180043ebd  xor     edi, edi
0x180043ebf  test    r12d, r12d
0x180043ec2  jz      short loc_180043EFE
0x180043ec4  mov     rax, [r14]
0x180043ec7  mov     r13d, edi
0x180043eca  mov     rcx, [rax+rdi*8]
0x180043ece  mov     rax, [rcx]
0x180043ed1  mov     rax, [rax+18h]
0x180043ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043eda  cmp     ax, r15w
0x180043ede  jnz     short loc_180043EF7
0x180043ee0  mov     rax, [r14]
0x180043ee3  mov     rcx, [rax+rdi*8]
0x180043ee7  mov     rax, [rcx]
0x180043eea  mov     rax, [rax+20h]
0x180043eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ef3  cmp     eax, ebp
0x180043ef5  jz      short loc_180043F37
0x180043ef7  inc     edi
0x180043ef9  cmp     edi, r12d
0x180043efc  jb      short loc_180043EC4
0x180043efe  lea     r8, [rsp+88h+arg_0]; struct IFSCameraControlState **
0x180043f06  mov     [rsp+88h+arg_0], 0
0x180043f12  mov     edx, ebp; unsigned int
0x180043f14  movzx   ecx, r15w; unsigned __int16
0x180043f18  call    ?CreateCameraControlState@FSCameraControlState@@SAJGIPEAPEAUIFSCameraControlState@@@Z; FSCameraControlState::CreateCameraControlState(ushort,uint,IFSCameraControlState * *)
0x180043f1d  mov     edi, eax
0x180043f1f  test    eax, eax
0x180043f21  jns     short loc_180043F4E
0x180043f23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f2a  jb      short loc_180043F91
0x180043f2c  mov     edx, 18h
0x180043f31  mov     [rsp+88h+var_68], eax
0x180043f35  jmp     short loc_180043F77
0x180043f37  mov     rax, [r14]
0x180043f3a  xor     edi, edi
0x180043f3c  mov     rcx, [rax+r13*8]
0x180043f40  mov     rax, [rcx]
0x180043f43  mov     rax, [rax+30h]
0x180043f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f4c  jmp     short loc_180043FBB
0x180043f4e  mov     rdx, [rsp+88h+arg_0]
0x180043f56  mov     rcx, r14
0x180043f59  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x180043f5e  test    eax, eax
0x180043f60  jnz     short loc_180043FAE
0x180043f62  mov     edi, 8007000Eh
0x180043f67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f6e  jb      short loc_180043F91
0x180043f70  lea     edx, [rax+19h]
0x180043f73  mov     [rsp+88h+var_68], edi
0x180043f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f7e  lea     r8, WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids
0x180043f85  mov     r9, rsi
0x180043f88  mov     rcx, [rcx+10h]
0x180043f8c  call    WPP_SF_qD
0x180043f91  lea     rcx, [rsp+88h+arg_0]
0x180043f99  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180043f9e  cmp     cs:byte_18005E5A5, 8
0x180043fa5  jb      short loc_180043FF6
0x180043fa7  mov     edx, 1Bh
0x180043fac  jmp     short loc_180043FD3
0x180043fae  lea     rcx, [rsp+88h+arg_0]
0x180043fb6  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180043fbb  call    cs:__imp_MFGetSystemTime
0x180043fc1  mov     [rsi+78h], rax
0x180043fc5  cmp     cs:byte_18005E5A5, 8
0x180043fcc  jb      short loc_180043FF6
0x180043fce  mov     edx, 1Ah
0x180043fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180043fda  mov     r9, rsi
0x180043fdd  mov     [rsp+88h+var_50], ebp
0x180043fe1  mov     [rsp+88h+var_58], r15d
0x180043fe6  mov     [rsp+88h+var_68], edi
0x180043fea  mov     rcx, [rcx+0D8h]
0x180043ff1  call    WPP_SF_qDsDD
0x180043ff6  lea     rcx, [rsi+8]; lpCriticalSection
0x180043ffa  call    cs:__imp_LeaveCriticalSection
0x180044000  mov     eax, edi
0x180044002  add     rsp, 48h
0x180044006  pop     r15
0x180044008  pop     r14
0x18004400a  pop     r13
0x18004400c  pop     r12
0x18004400e  pop     rdi
0x18004400f  pop     rsi
0x180044010  pop     rbp
0x180044011  pop     rbx
0x180044012  retn
```
