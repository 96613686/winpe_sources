# CPropertyCache::GetPropertyULong(ulong,ulong *)

- ea: `0x140016d00`
- end: `0x140016e27`
- name: `?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z`
- size: `295`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned int *)`
- caller_count: `45`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140019290`
- `0x1400198b4`
- `0x1400295b4`
- `0x14002a34c`
- `0x140033378`
- `0x140037930`
- `0x140038174`
- `0x140038c74`
- `0x140039164`
- `0x1400553f8`
- `0x1400587e0`
- `0x14005c7b0`
- `0x14005c9b0`
- `0x14005cca0`
- `0x14005cf88`
- `0x140061d58`
- `0x1400625a0`
- `0x1400671c8`
- `0x1400680e8`
- `0x14006b040`
- `0x140072960`
- `0x14007bbd0`
- `0x14007c140`
- `0x14007d030`
- `0x14007d4e0`
- `0x14007d640`
- `0x14007d7c0`
- `0x14007da78`
- `0x14007f07c`
- `0x140081290`
- `0x140088270`
- `0x14008af8c`
- `0x14008c430`
- `0x140091208`
- `0x140095e14`
- `0x14009d400`
- `0x1400a5fec`
- `0x1400a621c`
- `0x1400a7c7c`
- `0x1400a8210`
- `0x1400abc80`
- `0x1400b9c50`
- `0x1400c18a0`
- `0x1400c20b0`
- `0x1400c6450`

## callees

- `0x14000c778`
- `0x140016d00`

## pseudocode

```c
__int64 __fastcall CPropertyCache::GetPropertyULong(CPropertyCache *this, unsigned int a2, unsigned int *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v8; // [rsp+28h] [rbp-30h]
  int v9; // [rsp+28h] [rbp-30h]
  int v10; // [rsp+28h] [rbp-30h]

  v3 = 0;
  if ( a2 >= *((_DWORD *)this + 2) )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v10 = a2;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v10);
  }
  else
  {
    v5 = 56LL * a2 + *((_QWORD *)this + 2);
    if ( *(_BYTE *)(v5 + 8) )
    {
      v3 = v5;
    }
    else
    {
      if ( !*(_QWORD *)(v5 + 48) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v9 = a2;
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            20,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v9);
        }
        v6 = -1073741436;
        goto LABEL_5;
      }
      v3 = *(_QWORD *)(v5 + 48);
    }
    v6 = 0;
  }
LABEL_5:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v8) = v6;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      22,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v8);
  }
  if ( !v6 )
    *a3 = *(_DWORD *)(v3 + 16);
  return v6;
}

```

## disassembly

```asm
0x140016d00  push    rbx
0x140016d02  push    rbp
0x140016d03  push    rsi
0x140016d04  push    rdi
0x140016d05  push    r14
0x140016d07  sub     rsp, 30h
0x140016d0b  xor     edi, edi
0x140016d0d  lea     rbp, WPP_RECORDER_INITIALIZED
0x140016d14  lea     r14, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140016d1b  mov     rsi, r8
0x140016d1e  cmp     edx, [rcx+8]
0x140016d21  jnb     loc_140016DDF
0x140016d27  mov     rcx, [rcx+10h]
0x140016d2b  mov     eax, edx
0x140016d2d  imul    r9, rax, 38h ; '8'
0x140016d31  add     rcx, r9
0x140016d34  cmp     [rcx+8], dil
0x140016d38  jz      short loc_140016D94
0x140016d3a  mov     rdi, rcx
0x140016d3d  xor     ebx, ebx
0x140016d3f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140016d46  jnz     short loc_140016D5E
0x140016d48  test    ebx, ebx
0x140016d4a  jz      loc_140016E1D
0x140016d50  mov     eax, ebx
0x140016d52  add     rsp, 30h
0x140016d56  pop     r14
0x140016d58  pop     rdi
0x140016d59  pop     rsi
0x140016d5a  pop     rbp
0x140016d5b  pop     rbx
0x140016d5c  retn
0x140016d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d65  cmp     byte ptr [rcx+29h], 5
0x140016d69  jnb     short loc_140016D72
0x140016d6b  cmp     word ptr [rcx+48h], 0
0x140016d70  jz      short loc_140016D48
0x140016d72  mov     rcx, [rcx+40h]
0x140016d76  mov     r9d, 16h
0x140016d7c  mov     dword ptr [rsp+58h+var_30], ebx
0x140016d80  mov     r8d, 1
0x140016d86  mov     dl, 5
0x140016d88  mov     [rsp+58h+var_38], r14
0x140016d8d  call    WPP_RECORDER_SF_d
0x140016d92  jmp     short loc_140016D48
0x140016d94  mov     rax, [rcx+30h]
0x140016d98  test    rax, rax
0x140016d9b  jnz     short loc_140016DD7
0x140016d9d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140016da4  jz      short loc_140016DCD
0x140016da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140016dad  mov     r9d, 14h
0x140016db3  mov     dword ptr [rsp+58h+var_30], edx
0x140016db7  mov     r8d, 1
0x140016dbd  mov     dl, 4
0x140016dbf  mov     [rsp+58h+var_38], r14
0x140016dc4  mov     rcx, [rcx+40h]
0x140016dc8  call    WPP_RECORDER_SF_d
0x140016dcd  mov     ebx, 0C0000184h
0x140016dd2  jmp     loc_140016D3F
0x140016dd7  mov     rdi, rax
0x140016dda  jmp     loc_140016D3D
0x140016ddf  mov     ebx, 0C000000Dh
0x140016de4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140016deb  jz      loc_140016D50
0x140016df1  mov     rcx, cs:WPP_GLOBAL_Control
0x140016df8  mov     r9d, 13h
0x140016dfe  mov     dword ptr [rsp+58h+var_30], edx
0x140016e02  mov     r8d, 1
0x140016e08  mov     dl, 2
0x140016e0a  mov     [rsp+58h+var_38], r14
0x140016e0f  mov     rcx, [rcx+40h]
0x140016e13  call    WPP_RECORDER_SF_d
0x140016e18  jmp     loc_140016D3F
0x140016e1d  mov     eax, [rdi+10h]
0x140016e20  mov     [rsi], eax
0x140016e22  jmp     loc_140016D50
```
