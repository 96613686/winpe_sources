# SmRegisterUninstallStringWithSessionOrigin

- ea: `0x140007e00`
- end: `0x140007eaa`
- name: `SmRegisterUninstallStringWithSessionOrigin`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140007410`

## callees

- `0x140001020`
- `0x140001044`
- `0x140001068`
- `0x140001088`
- `0x1400011b0`
- `0x140001920`
- `0x140007e00`

## pseudocode

```c
__int64 __fastcall SmRegisterUninstallStringWithSessionOrigin(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // edi
  _QWORD *TrackSessionOriginDataLocked; // rax
  _QWORD *v8; // rsi
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rdx

  v6 = 0;
  if ( SmGetTrackSessionOriginData() )
  {
    SmAcquireTrackLockExclusive();
    TrackSessionOriginDataLocked = (_QWORD *)SmGetTrackSessionOriginDataLocked();
    v8 = TrackSessionOriginDataLocked;
    if ( TrackSessionOriginDataLocked )
    {
      v9 = (_QWORD *)*TrackSessionOriginDataLocked;
      while ( memcmp((const void *)(a1 + 32), (const void *)(v9[4] + 32LL), 0x10u) )
      {
        v9 = (_QWORD *)*v9;
        if ( v9 == v8 )
          goto LABEL_11;
      }
      v10 = (_QWORD *)SmAllocUninstallStringData(a2, a3);
      if ( v10 )
      {
        v11 = (_QWORD *)v9[7];
        if ( (_QWORD *)*v11 != v9 + 6 )
          __fastfail(3u);
        *v10 = v9 + 6;
        v10[1] = v11;
        *v11 = v10;
        v9[7] = v10;
      }
      else
      {
        v6 = -1073741801;
      }
    }
LABEL_11:
    SmReleaseTrackLock();
  }
  return v6;
}

```

## disassembly

```asm
0x140007e00  push    rbx
0x140007e02  push    rbp
0x140007e03  push    rsi
0x140007e04  push    rdi
0x140007e05  push    r14
0x140007e07  push    r15
0x140007e09  sub     rsp, 28h
0x140007e0d  mov     rbp, r8
0x140007e10  mov     r14, rdx
0x140007e13  mov     r15, rcx
0x140007e16  xor     edi, edi
0x140007e18  call    SmGetTrackSessionOriginData
0x140007e1d  test    rax, rax
0x140007e20  jz      short loc_140007E9A
0x140007e22  call    SmAcquireTrackLockExclusive
0x140007e27  call    SmGetTrackSessionOriginDataLocked
0x140007e2c  mov     rsi, rax
0x140007e2f  test    rax, rax
0x140007e32  jz      short loc_140007E95
0x140007e34  mov     rbx, [rax]
0x140007e37  jmp     short loc_140007E41
0x140007e39  mov     rbx, [rbx]
0x140007e3c  cmp     rbx, rsi
0x140007e3f  jz      short loc_140007E95
0x140007e41  mov     rdx, [rbx+20h]
0x140007e45  lea     rcx, [r15+20h]; Buf1
0x140007e49  add     rdx, 20h ; ' '; Buf2
0x140007e4d  mov     r8d, 10h; Size
0x140007e53  call    memcmp
0x140007e58  test    eax, eax
0x140007e5a  jnz     short loc_140007E39
0x140007e5c  mov     rdx, rbp
0x140007e5f  mov     rcx, r14
0x140007e62  call    SmAllocUninstallStringData
0x140007e67  test    rax, rax
0x140007e6a  jnz     short loc_140007E73
0x140007e6c  mov     edi, 0C0000017h
0x140007e71  jmp     short loc_140007E95
0x140007e73  lea     rcx, [rbx+30h]
0x140007e77  mov     rdx, [rcx+8]
0x140007e7b  cmp     [rdx], rcx
0x140007e7e  jz      short loc_140007E87
0x140007e80  mov     ecx, 3
0x140007e85  int     29h; Win8: RtlFailFast(ecx)
0x140007e87  mov     [rax], rcx
0x140007e8a  mov     [rax+8], rdx
0x140007e8e  mov     [rdx], rax
0x140007e91  mov     [rcx+8], rax
0x140007e95  call    SmReleaseTrackLock
0x140007e9a  mov     eax, edi
0x140007e9c  add     rsp, 28h
0x140007ea0  pop     r15
0x140007ea2  pop     r14
0x140007ea4  pop     rdi
0x140007ea5  pop     rsi
0x140007ea6  pop     rbp
0x140007ea7  pop     rbx
0x140007ea8  retn
```
