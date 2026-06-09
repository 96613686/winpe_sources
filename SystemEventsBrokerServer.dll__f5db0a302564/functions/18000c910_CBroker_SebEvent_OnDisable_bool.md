# CBroker::SebEvent::OnDisable(bool)

- ea: `0x18000c910`
- end: `0x18000cb3b`
- name: `?OnDisable@SebEvent@CBroker@@QEAAX_N@Z`
- size: `555`
- prototype: `void __fastcall(CBroker::SebEvent *__hidden this, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c30`
- `0x18000b3d0`
- `0x18001b378`
- `0x18001bcdc`

## callees

- `0x180003950`
- `0x180003af0`
- `0x180008c00`
- `0x18000c910`
- `0x18001d9ac`
- `0x180020948`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c933`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cacc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c933`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cacc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c98c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c9e9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c98c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c9e9`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000c9ff`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000c9ff`
- `ntdll!RtlWakeAddressAll` at `0x18000c983`
- `ntdll!RtlWakeAddressAll` at `0x18000c983`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000c9bc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000c9bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c939`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c939`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBroker::SebEvent::OnDisable(CBroker::SebEvent *this, char a2)
{
  char *v4; // rbx
  __int64 v5; // rdx
  char v6; // bp
  _QWORD *v7; // rcx
  __int64 v8; // r14
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r8
  char *v12; // [rsp+30h] [rbp-68h]
  void **pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  __int128 v14; // [rsp+48h] [rbp-50h]
  int v15; // [rsp+58h] [rbp-40h]

  v4 = (char *)this + 240;
  v12 = (char *)this + 240;
  RtlAcquireSRWLockExclusive((char *)this + 240);
  GetCurrentThreadId();
  v6 = 1;
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
      *((unsigned int *)this + 28),
      *((_DWORD *)this + 29));
    v7 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 38) )
  {
    v8 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = 0;
    *((_DWORD *)this + 38) = 0;
    RtlWakeAddressAll((char *)this + 152, v5);
    RtlReleaseSRWLockExclusive(v4);
    v6 = 0;
    if ( v8 )
    {
      if ( a2 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
            *((unsigned int *)this + 28),
            *((_DWORD *)this + 29));
        v10 = RtlUnsubscribeWnfNotificationWaitForCompletion(v8);
      }
      else
      {
        v10 = RtlUnsubscribeWnfStateChangeNotification(v8);
      }
      if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741772 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_DDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            WPP_GLOBAL_Control,
            v11,
            *((unsigned int *)this + 28),
            *((_DWORD *)this + 29),
            v10,
            v12,
            0);
        v14 = 0;
        v15 = 7;
        pExceptionObject = &Broker::EventInternalError::`vftable';
        throw (Broker::EventInternalError *)&pExceptionObject;
      }
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          v9,
          *((unsigned int *)this + 28),
          *((_DWORD *)this + 29),
          *((_DWORD *)this + 38));
      RtlAcquireSRWLockExclusive(v4);
      GetCurrentThreadId();
      v6 = 1;
    }
    v7 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF__guid_(v7[2], 44, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
  if ( v6 )
    RtlReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x18000c910  push    rbx
0x18000c912  push    rbp
0x18000c913  push    rsi
0x18000c914  push    rdi
0x18000c915  push    r14
0x18000c917  push    r15
0x18000c919  sub     rsp, 68h
0x18000c91d  movzx   r15d, dl
0x18000c921  mov     rsi, rcx
0x18000c924  lea     rbx, [rcx+0F0h]
0x18000c92b  mov     [rsp+98h+var_68], rbx
0x18000c930  mov     rcx, rbx
0x18000c933  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000c939  call    cs:__imp_GetCurrentThreadId
0x18000c93f  mov     [rsp+98h+var_5C], eax
0x18000c943  mov     bpl, 1
0x18000c946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c94d  test    byte ptr [rcx+1Ch], 40h
0x18000c951  jz      short loc_18000C95D
0x18000c953  cmp     byte ptr [rcx+19h], 4
0x18000c957  jnb     loc_18000CA90
0x18000c95d  cmp     dword ptr [rsi+98h], 0
0x18000c964  jz      short loc_18000C9D7
0x18000c966  mov     r14, [rsi+0A8h]
0x18000c96d  xor     eax, eax
0x18000c96f  mov     [rsi+0A8h], rax
0x18000c976  mov     [rsi+98h], eax
0x18000c97c  lea     rcx, [rsi+98h]
0x18000c983  call    cs:__imp_RtlWakeAddressAll
0x18000c989  mov     rcx, rbx
0x18000c98c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000c992  xor     bpl, bpl
0x18000c995  mov     [rsp+98h+var_60], bpl
0x18000c99a  test    r14, r14
0x18000c99d  jz      loc_18000CABC
0x18000c9a3  test    r15b, r15b
0x18000c9a6  jz      short loc_18000C9FC
0x18000c9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9af  test    byte ptr [rcx+1Ch], 1
0x18000c9b3  jnz     loc_18000CAE0
0x18000c9b9  mov     rcx, r14
0x18000c9bc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000c9c2  mov     ecx, eax
0x18000c9c4  mov     edx, 80000000h
0x18000c9c9  lea     eax, [rax+rdx]
0x18000c9cc  test    edx, eax
0x18000c9ce  jz      short loc_18000CA07
0x18000c9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9d7  test    byte ptr [rcx+1Ch], 40h
0x18000c9db  jnz     loc_18000CA68
0x18000c9e1  test    bpl, bpl
0x18000c9e4  jz      short loc_18000C9EF
0x18000c9e6  mov     rcx, rbx
0x18000c9e9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000c9ef  add     rsp, 68h
0x18000c9f3  pop     r15
0x18000c9f5  pop     r14
0x18000c9f7  pop     rdi
0x18000c9f8  pop     rsi
0x18000c9f9  pop     rbp
0x18000c9fa  pop     rbx
0x18000c9fb  retn
0x18000c9fc  mov     rcx, r14
0x18000c9ff  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18000ca05  jmp     short loc_18000C9C2
0x18000ca07  cmp     ecx, 0C0000034h
0x18000ca0d  jz      short loc_18000C9D0
0x18000ca0f  mov     rdx, cs:WPP_GLOBAL_Control
0x18000ca16  test    byte ptr [rdx+1Ch], 40h
0x18000ca1a  jz      short loc_18000CA3A
0x18000ca1c  cmp     byte ptr [rdx+19h], 2
0x18000ca20  jb      short loc_18000CA3A
0x18000ca22  mov     [rsp+98h+var_70], ecx
0x18000ca26  mov     eax, [rsi+74h]
0x18000ca29  mov     [rsp+98h+var_78], eax
0x18000ca2d  mov     r9d, [rsi+70h]
0x18000ca31  mov     rcx, [rdx+10h]
0x18000ca35  call    WPP_SF_DDD
0x18000ca3a  xorps   xmm0, xmm0
0x18000ca3d  movups  [rsp+98h+var_50], xmm0
0x18000ca42  mov     [rsp+98h+var_40], 7
0x18000ca4a  lea     rax, ??_7EventInternalError@Broker@@6B@; const Broker::EventInternalError::`vftable'
0x18000ca51  mov     [rsp+98h+pExceptionObject], rax
0x18000ca56  lea     rdx, _TI3?AUEventInternalError@Broker@@; pThrowInfo
0x18000ca5d  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000ca62  call    _CxxThrowException_0
0x18000ca68  cmp     byte ptr [rcx+19h], 4
0x18000ca6c  jb      loc_18000C9E1
0x18000ca72  lea     r9, [rsi+78h]
0x18000ca76  mov     edx, 2Ch ; ','
0x18000ca7b  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000ca82  mov     rcx, [rcx+10h]
0x18000ca86  call    WPP_SF__guid_
0x18000ca8b  jmp     loc_18000C9E1
0x18000ca90  mov     edx, 28h ; '('
0x18000ca95  mov     eax, [rsi+74h]
0x18000ca98  mov     [rsp+98h+var_78], eax
0x18000ca9c  mov     r9d, [rsi+70h]
0x18000caa0  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000caa7  mov     rcx, [rcx+10h]
0x18000caab  call    WPP_SF_DD
0x18000cab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cab7  jmp     loc_18000C95D
0x18000cabc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cac3  test    byte ptr [rcx+1Ch], 40h
0x18000cac7  jnz     short loc_18000CB0F
0x18000cac9  mov     rcx, rbx
0x18000cacc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000cad2  call    cs:__imp_GetCurrentThreadId
0x18000cad8  mov     bpl, 1
0x18000cadb  jmp     loc_18000C9D0
0x18000cae0  cmp     byte ptr [rcx+19h], 4
0x18000cae4  jb      loc_18000C9B9
0x18000caea  mov     edx, 2Ah ; '*'
0x18000caef  mov     eax, [rsi+74h]
0x18000caf2  mov     [rsp+98h+var_78], eax
0x18000caf6  mov     r9d, [rsi+70h]
0x18000cafa  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000cb01  mov     rcx, [rcx+10h]
0x18000cb05  call    WPP_SF_DD
0x18000cb0a  jmp     loc_18000C9B9
0x18000cb0f  cmp     byte ptr [rcx+19h], 2
0x18000cb13  jb      short loc_18000CAC9
0x18000cb15  mov     edx, 29h ; ')'
0x18000cb1a  mov     eax, [rsi+98h]
0x18000cb20  mov     [rsp+98h+var_70], eax
0x18000cb24  mov     eax, [rsi+74h]
0x18000cb27  mov     [rsp+98h+var_78], eax
0x18000cb2b  mov     r9d, [rsi+70h]
0x18000cb2f  mov     rcx, [rcx+10h]
0x18000cb33  call    WPP_SF_DDd
0x18000cb38  jmp     short loc_18000CAC9
```
