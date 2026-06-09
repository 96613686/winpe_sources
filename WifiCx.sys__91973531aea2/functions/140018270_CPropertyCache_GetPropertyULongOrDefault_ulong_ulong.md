# CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)

- ea: `0x140018270`
- end: `0x1400183b7`
- name: `?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z`
- size: `327`
- prototype: `unsigned int __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned int)`
- caller_count: `27`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011f9c`
- `0x140014344`
- `0x14002a34c`
- `0x14002de30`
- `0x14002e5f0`
- `0x140030b60`
- `0x140030d88`
- `0x140032d30`
- `0x140032f4c`
- `0x14007f588`
- `0x14007f7a0`
- `0x140080730`
- `0x140083884`
- `0x140084068`
- `0x140088778`
- `0x140089258`
- `0x1400898c0`
- `0x140091208`
- `0x140092734`
- `0x1400aad50`
- `0x1400aced0`
- `0x1400adae0`
- `0x1400af6b8`
- `0x1400af7a8`
- `0x1400b4d60`
- `0x1400b511c`
- `0x1400b9ea0`

## callees

- `0x1400069dc`
- `0x14000c778`
- `0x140018270`

## pseudocode

```c
__int64 __fastcall CPropertyCache::GetPropertyULongOrDefault(CPropertyCache *this, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rsi
  char v4; // di
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v9; // [rsp+28h] [rbp-50h]
  int v10; // [rsp+28h] [rbp-50h]
  int v11; // [rsp+28h] [rbp-50h]

  v3 = 0;
  v4 = a2;
  if ( a2 >= *((_DWORD *)this + 2) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return a3;
    v11 = a2;
    LOBYTE(a2) = 2;
    v7 = -1073741811;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v11);
  }
  else
  {
    v6 = 56LL * a2 + *((_QWORD *)this + 2);
    if ( *(_BYTE *)(v6 + 8) )
    {
      v3 = v6;
    }
    else
    {
      if ( !*(_QWORD *)(v6 + 48) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = a2;
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            20,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v10);
        }
        v7 = -1073741436;
        goto LABEL_12;
      }
      v3 = *(_QWORD *)(v6 + 48);
    }
    v7 = 0;
  }
LABEL_12:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v9) = v7;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      22,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v9);
  }
  if ( !v7 )
    return *(unsigned int *)(v3 + 16);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      18,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v4,
      v7);
  }
  return a3;
}

```

## disassembly

```asm
0x140018270  push    rbx
0x140018272  push    rbp
0x140018273  push    rsi
0x140018274  push    rdi
0x140018275  push    r14
0x140018277  push    r15
0x140018279  sub     rsp, 48h
0x14001827d  xor     esi, esi
0x14001827f  mov     edi, edx
0x140018281  lea     r14, WPP_RECORDER_INITIALIZED
0x140018288  mov     ebp, r8d
0x14001828b  lea     r15, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140018292  cmp     edx, [rcx+8]
0x140018295  jnb     short loc_1400182F4
0x140018297  mov     rcx, [rcx+10h]
0x14001829b  imul    r8, rdi, 38h ; '8'
0x14001829f  add     rcx, r8
0x1400182a2  cmp     [rcx+8], sil
0x1400182a6  jnz     short loc_1400182ED
0x1400182a8  mov     rax, [rcx+30h]
0x1400182ac  test    rax, rax
0x1400182af  jnz     short loc_1400182E8
0x1400182b1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400182b8  jz      short loc_1400182E1
0x1400182ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182c1  mov     r9d, 14h
0x1400182c7  mov     dword ptr [rsp+78h+var_50], edi
0x1400182cb  mov     r8d, 1
0x1400182d1  mov     dl, 4
0x1400182d3  mov     [rsp+78h+var_58], r15
0x1400182d8  mov     rcx, [rcx+40h]
0x1400182dc  call    WPP_RECORDER_SF_d
0x1400182e1  mov     ebx, 0C0000184h
0x1400182e6  jmp     short loc_14001832D
0x1400182e8  mov     rsi, rax
0x1400182eb  jmp     short loc_1400182F0
0x1400182ed  mov     rsi, rcx
0x1400182f0  xor     ebx, ebx
0x1400182f2  jmp     short loc_14001832D
0x1400182f4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400182fb  jz      loc_1400183A7
0x140018301  mov     rcx, cs:WPP_GLOBAL_Control
0x140018308  mov     r9d, 13h
0x14001830e  mov     dword ptr [rsp+78h+var_50], edi
0x140018312  mov     r8d, 1
0x140018318  mov     dl, 2
0x14001831a  mov     [rsp+78h+var_58], r15
0x14001831f  mov     ebx, 0C000000Dh
0x140018324  mov     rcx, [rcx+40h]
0x140018328  call    WPP_RECORDER_SF_d
0x14001832d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140018334  jz      short loc_14001836A
0x140018336  mov     rcx, cs:WPP_GLOBAL_Control
0x14001833d  cmp     byte ptr [rcx+29h], 5
0x140018341  jnb     short loc_14001834A
0x140018343  cmp     word ptr [rcx+48h], 0
0x140018348  jz      short loc_14001836A
0x14001834a  mov     rcx, [rcx+40h]
0x14001834e  mov     r9d, 16h
0x140018354  mov     dword ptr [rsp+78h+var_50], ebx
0x140018358  mov     r8d, 1
0x14001835e  mov     dl, 5
0x140018360  mov     [rsp+78h+var_58], r15
0x140018365  call    WPP_RECORDER_SF_d
0x14001836a  test    ebx, ebx
0x14001836c  jnz     short loc_140018373
0x14001836e  mov     eax, [rsi+10h]
0x140018371  jmp     short loc_1400183A9
0x140018373  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001837a  jz      short loc_1400183A7
0x14001837c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018383  mov     r9d, 12h
0x140018389  mov     [rsp+78h+var_48], ebx
0x14001838d  mov     r8d, 1
0x140018393  mov     dword ptr [rsp+78h+var_50], edi
0x140018397  mov     dl, 4
0x140018399  mov     [rsp+78h+var_58], r15
0x14001839e  mov     rcx, [rcx+40h]
0x1400183a2  call    WPP_RECORDER_SF_DD
0x1400183a7  mov     eax, ebp
0x1400183a9  add     rsp, 48h
0x1400183ad  pop     r15
0x1400183af  pop     r14
0x1400183b1  pop     rdi
0x1400183b2  pop     rsi
0x1400183b3  pop     rbp
0x1400183b4  pop     rbx
0x1400183b5  retn
```
