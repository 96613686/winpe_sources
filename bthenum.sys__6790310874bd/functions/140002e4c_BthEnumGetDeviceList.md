# BthEnumGetDeviceList

- ea: `0x140002e4c`
- end: `0x14000304b`
- name: `BthEnumGetDeviceList`
- size: `511`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001cf90`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x140002e4c`
- `0x14001f054`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140002f51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002f51`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002f67`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002f67`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002fe8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002fe8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002ff4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002ff4`
- `ntoskrnl!ExFreePool` at `0x140002f45`
- `ntoskrnl!ExFreePool` at `0x140002f45`
- `ntoskrnl!ExAllocatePool2` at `0x140002ed7`
- `ntoskrnl!ExAllocatePool2` at `0x140002ed7`

## pseudocode

```c
__int64 __fastcall BthEnumGetDeviceList(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rbx
  unsigned int v4; // edi
  unsigned __int64 v6; // rax
  unsigned int v7; // eax
  _DWORD *Pool2; // rax
  _DWORD *v9; // rsi
  unsigned int v10; // edi
  __int64 i; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  _QWORD *v15; // rdx
  __int64 v16; // rbx
  unsigned __int64 v17; // rax
  __int64 v19; // [rsp+28h] [rbp-50h]

  v2 = *(_DWORD **)(a2 + 56);
  v4 = *(_DWORD *)(a1 + 252);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      4,
      37,
      (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids);
  if ( v2 )
    v4 += *v2;
  v6 = 8LL * v4;
  if ( v6 <= 0xFFFFFFFF )
  {
    v7 = v6 + 16;
    if ( v7 >= 0x10 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(256, v7, 1330467906);
      v9 = Pool2;
      if ( !Pool2 )
      {
        v10 = -1073741670;
        goto LABEL_31;
      }
      v10 = 0;
      *Pool2 = 0;
      if ( v2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            3,
            38,
            (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
            *v2);
        for ( i = 0; (unsigned int)i < *v2; ++*v9 )
        {
          *(_QWORD *)&v9[2 * i + 2] = *(_QWORD *)&v2[2 * i + 2];
          i = (unsigned int)(i + 1);
        }
        ExFreePool(v2);
      }
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 152));
      v12 = *(_QWORD *)(a1 + 144);
      if ( (v12 & 1) != 0 )
      {
        if ( v12 == 1 )
        {
LABEL_29:
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 152));
          KeLeaveCriticalRegion();
          *(_QWORD *)(a2 + 56) = v9;
          goto LABEL_31;
        }
        v13 = v12 ^ ((a1 + 136) | 1);
      }
      else
      {
        v13 = *(_QWORD *)(a1 + 144);
      }
      if ( v13 )
      {
        do
        {
          v14 = *(_QWORD *)(v13 + 8);
          if ( v14 )
          {
            v15 = *(_QWORD **)v14;
            if ( *(_QWORD *)v14 )
            {
              do
              {
                v14 = (unsigned __int64)v15;
                v15 = (_QWORD *)*v15;
              }
              while ( v15 );
            }
          }
          else
          {
            v16 = *(_QWORD *)(v13 + 16);
            v17 = v13;
            while ( 1 )
            {
              v14 = v16 & 0xFFFFFFFFFFFFFFFCuLL;
              if ( !v14 || *(_QWORD *)v14 == v17 )
                break;
              v17 = v14;
              v16 = *(_QWORD *)(v14 + 16);
            }
          }
          BthEnumReportID(v13, v9);
          v13 = v14;
        }
        while ( v14 );
      }
      goto LABEL_29;
    }
  }
  v10 = -1073741675;
LABEL_31:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v19) = v10;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      4,
      39,
      (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
      v19);
  }
  return v10;
}

```

## disassembly

```asm
0x140002e4c  push    rbx
0x140002e4e  push    rbp
0x140002e4f  push    rsi
0x140002e50  push    rdi
0x140002e51  push    r12
0x140002e53  push    r13
0x140002e55  push    r14
0x140002e57  push    r15
0x140002e59  sub     rsp, 38h
0x140002e5d  mov     rbx, [rdx+38h]
0x140002e61  mov     r15, rdx
0x140002e64  mov     edi, [rcx+0FCh]
0x140002e6a  mov     rbp, rcx
0x140002e6d  lea     r12, WPP_RECORDER_INITIALIZED
0x140002e74  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002e7b  lea     r13, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140002e82  jz      short loc_140002EA3
0x140002e84  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e8b  mov     r9d, 25h ; '%'
0x140002e91  mov     [rsp+78h+var_58], r13
0x140002e96  mov     rcx, [rcx+40h]
0x140002e9a  lea     r8d, [r9-21h]
0x140002e9e  call    WPP_RECORDER_SF_
0x140002ea3  test    rbx, rbx
0x140002ea6  jz      short loc_140002EAA
0x140002ea8  add     edi, [rbx]
0x140002eaa  mov     eax, edi
0x140002eac  mov     ecx, 0FFFFFFFFh
0x140002eb1  shl     rax, 3
0x140002eb5  cmp     rax, rcx
0x140002eb8  ja      loc_140003006
0x140002ebe  add     eax, 10h
0x140002ec1  cmp     eax, 10h
0x140002ec4  jb      loc_140003006
0x140002eca  mov     edx, eax
0x140002ecc  mov     ecx, 100h
0x140002ed1  mov     r8d, 4F4D5442h
0x140002ed7  call    cs:__imp_ExAllocatePool2
0x140002ede  nop     dword ptr [rax+rax+00h]
0x140002ee3  mov     rsi, rax
0x140002ee6  test    rax, rax
0x140002ee9  jnz     short loc_140002EF5
0x140002eeb  mov     edi, 0C000009Ah
0x140002ef0  jmp     loc_14000300B
0x140002ef5  xor     edi, edi
0x140002ef7  mov     [rax], edi
0x140002ef9  test    rbx, rbx
0x140002efc  jz      short loc_140002F51
0x140002efe  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002f05  jz      short loc_140002F2A
0x140002f07  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f0e  lea     r9d, [rdi+26h]
0x140002f12  mov     eax, [rbx]
0x140002f14  lea     r8d, [rdi+3]
0x140002f18  mov     dword ptr [rsp+78h+var_50], eax
0x140002f1c  mov     [rsp+78h+var_58], r13
0x140002f21  mov     rcx, [rcx+40h]
0x140002f25  call    WPP_RECORDER_SF_d
0x140002f2a  xor     ecx, ecx
0x140002f2c  cmp     [rbx], ecx
0x140002f2e  jbe     short loc_140002F42
0x140002f30  mov     rax, [rbx+rcx*8+8]
0x140002f35  mov     [rsi+rcx*8+8], rax
0x140002f3a  inc     ecx
0x140002f3c  inc     dword ptr [rsi]
0x140002f3e  cmp     ecx, [rbx]
0x140002f40  jb      short loc_140002F30
0x140002f42  mov     rcx, rbx; P
0x140002f45  call    cs:__imp_ExFreePool
0x140002f4c  nop     dword ptr [rax+rax+00h]
0x140002f51  call    cs:__imp_KeEnterCriticalRegion
0x140002f58  nop     dword ptr [rax+rax+00h]
0x140002f5d  lea     r14, [rbp+98h]
0x140002f64  mov     rcx, r14; FastMutex
0x140002f67  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140002f6e  nop     dword ptr [rax+rax+00h]
0x140002f73  lea     rcx, [rbp+88h]
0x140002f7a  mov     rax, [rcx+8]
0x140002f7e  test    al, 1
0x140002f80  jz      short loc_140002F91
0x140002f82  cmp     rax, 1
0x140002f86  jz      short loc_140002FE5
0x140002f88  or      rcx, 1
0x140002f8c  xor     rcx, rax
0x140002f8f  jmp     short loc_140002F94
0x140002f91  mov     rcx, rax
0x140002f94  test    rcx, rcx
0x140002f97  jz      short loc_140002FE5
0x140002f99  mov     rbx, [rcx+8]
0x140002f9d  test    rbx, rbx
0x140002fa0  jz      short loc_140002FBA
0x140002fa2  mov     rdx, [rbx]
0x140002fa5  test    rdx, rdx
0x140002fa8  jz      short loc_140002FD5
0x140002faa  mov     rax, [rdx]
0x140002fad  mov     rbx, rdx
0x140002fb0  mov     rdx, rax
0x140002fb3  test    rax, rax
0x140002fb6  jnz     short loc_140002FAA
0x140002fb8  jmp     short loc_140002FD5
0x140002fba  mov     rbx, [rcx+10h]
0x140002fbe  mov     rax, rcx
0x140002fc1  jmp     short loc_140002FCF
0x140002fc3  cmp     [rbx], rax
0x140002fc6  jz      short loc_140002FD5
0x140002fc8  mov     rax, rbx
0x140002fcb  mov     rbx, [rbx+10h]
0x140002fcf  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140002fd3  jnz     short loc_140002FC3
0x140002fd5  mov     rdx, rsi
0x140002fd8  call    BthEnumReportID
0x140002fdd  mov     rcx, rbx
0x140002fe0  test    rbx, rbx
0x140002fe3  jnz     short loc_140002F99
0x140002fe5  mov     rcx, r14; FastMutex
0x140002fe8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140002fef  nop     dword ptr [rax+rax+00h]
0x140002ff4  call    cs:__imp_KeLeaveCriticalRegion
0x140002ffb  nop     dword ptr [rax+rax+00h]
0x140003000  mov     [r15+38h], rsi
0x140003004  jmp     short loc_14000300B
0x140003006  mov     edi, 0C0000095h
0x14000300b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140003012  jz      short loc_140003037
0x140003014  mov     rcx, cs:WPP_GLOBAL_Control
0x14000301b  mov     r9d, 27h ; '''
0x140003021  mov     dword ptr [rsp+78h+var_50], edi
0x140003025  mov     [rsp+78h+var_58], r13
0x14000302a  mov     rcx, [rcx+40h]
0x14000302e  lea     r8d, [r9-23h]
0x140003032  call    WPP_RECORDER_SF_d
0x140003037  mov     eax, edi
0x140003039  add     rsp, 38h
0x14000303d  pop     r15
0x14000303f  pop     r14
0x140003041  pop     r13
0x140003043  pop     r12
0x140003045  pop     rdi
0x140003046  pop     rsi
0x140003047  pop     rbp
0x140003048  pop     rbx
0x140003049  retn
```
