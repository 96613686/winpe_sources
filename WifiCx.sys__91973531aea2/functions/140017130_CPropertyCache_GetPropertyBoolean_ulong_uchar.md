# CPropertyCache::GetPropertyBoolean(ulong,uchar *)

- ea: `0x140017130`
- end: `0x140017258`
- name: `?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z`
- size: `296`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `26`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140018e10`
- `0x140025d50`
- `0x14002a34c`
- `0x14004e360`
- `0x14005c2dc`
- `0x14006a230`
- `0x1400723c0`
- `0x14007c140`
- `0x140084a9c`
- `0x14008642c`
- `0x140087eb8`
- `0x140089b84`
- `0x14008b344`
- `0x140091900`
- `0x14009d400`
- `0x14009f3e8`
- `0x1400a22d4`
- `0x1400a4d28`
- `0x1400a5520`
- `0x1400b0448`
- `0x1400b06f0`
- `0x1400b9ea0`
- `0x1400ba610`
- `0x1400bb8b0`
- `0x1400c4c60`
- `0x1400c6450`

## callees

- `0x14000c778`
- `0x140017130`

## pseudocode

```c
__int64 __fastcall CPropertyCache::GetPropertyBoolean(CPropertyCache *this, unsigned int a2, unsigned __int8 *a3)
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
    *a3 = *(_BYTE *)(v3 + 16);
  return v6;
}

```

## disassembly

```asm
0x140017130  push    rbx
0x140017132  push    rbp
0x140017133  push    rsi
0x140017134  push    rdi
0x140017135  push    r14
0x140017137  sub     rsp, 30h
0x14001713b  xor     edi, edi
0x14001713d  lea     rbp, WPP_RECORDER_INITIALIZED
0x140017144  lea     r14, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14001714b  mov     rsi, r8
0x14001714e  cmp     edx, [rcx+8]
0x140017151  jnb     loc_14001720F
0x140017157  mov     rcx, [rcx+10h]
0x14001715b  mov     eax, edx
0x14001715d  imul    r9, rax, 38h ; '8'
0x140017161  add     rcx, r9
0x140017164  cmp     [rcx+8], dil
0x140017168  jz      short loc_1400171C4
0x14001716a  mov     rdi, rcx
0x14001716d  xor     ebx, ebx
0x14001716f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140017176  jnz     short loc_14001718E
0x140017178  test    ebx, ebx
0x14001717a  jz      loc_14001724D
0x140017180  mov     eax, ebx
0x140017182  add     rsp, 30h
0x140017186  pop     r14
0x140017188  pop     rdi
0x140017189  pop     rsi
0x14001718a  pop     rbp
0x14001718b  pop     rbx
0x14001718c  retn
0x14001718e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017195  cmp     byte ptr [rcx+29h], 5
0x140017199  jnb     short loc_1400171A2
0x14001719b  cmp     word ptr [rcx+48h], 0
0x1400171a0  jz      short loc_140017178
0x1400171a2  mov     rcx, [rcx+40h]
0x1400171a6  mov     r9d, 16h
0x1400171ac  mov     dword ptr [rsp+58h+var_30], ebx
0x1400171b0  mov     r8d, 1
0x1400171b6  mov     dl, 5
0x1400171b8  mov     [rsp+58h+var_38], r14
0x1400171bd  call    WPP_RECORDER_SF_d
0x1400171c2  jmp     short loc_140017178
0x1400171c4  mov     rax, [rcx+30h]
0x1400171c8  test    rax, rax
0x1400171cb  jnz     short loc_140017207
0x1400171cd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400171d4  jz      short loc_1400171FD
0x1400171d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171dd  mov     r9d, 14h
0x1400171e3  mov     dword ptr [rsp+58h+var_30], edx
0x1400171e7  mov     r8d, 1
0x1400171ed  mov     dl, 4
0x1400171ef  mov     [rsp+58h+var_38], r14
0x1400171f4  mov     rcx, [rcx+40h]
0x1400171f8  call    WPP_RECORDER_SF_d
0x1400171fd  mov     ebx, 0C0000184h
0x140017202  jmp     loc_14001716F
0x140017207  mov     rdi, rax
0x14001720a  jmp     loc_14001716D
0x14001720f  mov     ebx, 0C000000Dh
0x140017214  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001721b  jz      loc_140017180
0x140017221  mov     rcx, cs:WPP_GLOBAL_Control
0x140017228  mov     r9d, 13h
0x14001722e  mov     dword ptr [rsp+58h+var_30], edx
0x140017232  mov     r8d, 1
0x140017238  mov     dl, 2
0x14001723a  mov     [rsp+58h+var_38], r14
0x14001723f  mov     rcx, [rcx+40h]
0x140017243  call    WPP_RECORDER_SF_d
0x140017248  jmp     loc_14001716F
0x14001724d  movzx   eax, byte ptr [rdi+10h]
0x140017251  mov     [rsi], al
0x140017253  jmp     loc_140017180
```
