# CPropertyCache::SetPropertyULong(ulong,ulong)

- ea: `0x14002aaec`
- end: `0x14002abb6`
- name: `?SetPropertyULong@CPropertyCache@@QEAAHKK@Z`
- size: `202`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned int)`
- caller_count: `33`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140014344`
- `0x1400198b4`
- `0x140020dc0`
- `0x140027530`
- `0x140029f1c`
- `0x14002de30`
- `0x14002e5f0`
- `0x140033378`
- `0x1400551d4`
- `0x1400581f8`
- `0x140067478`
- `0x140067578`
- `0x1400678c0`
- `0x140067f04`
- `0x1400680e8`
- `0x14006e5ec`
- `0x140072b40`
- `0x140073260`
- `0x140076f20`
- `0x140077c00`
- `0x140078bc0`
- `0x14007bbd0`
- `0x14007c140`
- `0x14007c4d0`
- `0x14007f588`
- `0x140080730`
- `0x140089258`
- `0x14008ba40`
- `0x14009c100`
- `0x1400abc80`
- `0x1400adae0`
- `0x1400b511c`
- `0x1400be190`

## callees

- `0x14000c778`
- `0x14002aaec`

## pseudocode

```c
__int64 __fastcall CPropertyCache::SetPropertyULong(CPropertyCache *this, unsigned int a2, int a3)
{
  unsigned int v4; // ebp
  unsigned int v5; // edi
  __int64 v6; // rbx
  __int64 v8; // [rsp+28h] [rbp-40h]
  int v9; // [rsp+28h] [rbp-40h]

  v4 = a2;
  if ( a2 >= *((_DWORD *)this + 2) )
  {
    v5 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v5;
    v9 = a2;
    LOBYTE(a2) = 2;
    v6 = 0;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v9);
  }
  else
  {
    v5 = 0;
    v6 = *((_QWORD *)this + 2) + 56LL * a2;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v8) = v5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        22,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v8);
    }
  }
  if ( !v5 )
  {
    *(_DWORD *)v6 = v4;
    *(_DWORD *)(v6 + 4) = 1;
    *(_DWORD *)(v6 + 16) = a3;
    *(_BYTE *)(v6 + 8) = 1;
  }
  return v5;
}

```

## disassembly

```asm
0x14002aaec  push    rbx
0x14002aaee  push    rbp
0x14002aaef  push    rsi
0x14002aaf0  push    rdi
0x14002aaf1  push    r12
0x14002aaf3  push    r13
0x14002aaf5  push    r14
0x14002aaf7  sub     rsp, 30h
0x14002aafb  lea     r12, WPP_RECORDER_INITIALIZED
0x14002ab02  mov     r14d, r8d
0x14002ab05  lea     r13, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14002ab0c  mov     ebp, edx
0x14002ab0e  cmp     edx, [rcx+8]
0x14002ab11  jnb     short loc_14002AB21
0x14002ab13  xor     esi, esi
0x14002ab15  imul    rbx, rbp, 38h ; '8'
0x14002ab19  mov     edi, esi
0x14002ab1b  add     rbx, [rcx+10h]
0x14002ab1f  jmp     short loc_14002AB56
0x14002ab21  mov     edi, 0C000000Dh
0x14002ab26  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002ab2d  jz      short loc_14002ABA4
0x14002ab2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab36  xor     esi, esi
0x14002ab38  mov     dword ptr [rsp+68h+var_40], ebp
0x14002ab3c  mov     dl, 2
0x14002ab3e  mov     ebx, esi
0x14002ab40  mov     [rsp+68h+var_48], r13
0x14002ab45  mov     rcx, [rcx+40h]
0x14002ab49  lea     r9d, [rsi+13h]
0x14002ab4d  lea     r8d, [rsi+1]
0x14002ab51  call    WPP_RECORDER_SF_d
0x14002ab56  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002ab5d  jz      short loc_14002AB8F
0x14002ab5f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab66  mov     dl, 5
0x14002ab68  cmp     [rcx+29h], dl
0x14002ab6b  jnb     short loc_14002AB73
0x14002ab6d  cmp     [rcx+48h], si
0x14002ab71  jz      short loc_14002AB8F
0x14002ab73  mov     rcx, [rcx+40h]
0x14002ab77  mov     r9d, 16h
0x14002ab7d  mov     dword ptr [rsp+68h+var_40], edi
0x14002ab81  mov     [rsp+68h+var_48], r13
0x14002ab86  lea     r8d, [r9-15h]
0x14002ab8a  call    WPP_RECORDER_SF_d
0x14002ab8f  test    edi, edi
0x14002ab91  jnz     short loc_14002ABA4
0x14002ab93  mov     [rbx], ebp
0x14002ab95  mov     dword ptr [rbx+4], 1
0x14002ab9c  mov     [rbx+10h], r14d
0x14002aba0  mov     byte ptr [rbx+8], 1
0x14002aba4  mov     eax, edi
0x14002aba6  add     rsp, 30h
0x14002abaa  pop     r14
0x14002abac  pop     r13
0x14002abae  pop     r12
0x14002abb0  pop     rdi
0x14002abb1  pop     rsi
0x14002abb2  pop     rbp
0x14002abb3  pop     rbx
0x14002abb4  retn
```
