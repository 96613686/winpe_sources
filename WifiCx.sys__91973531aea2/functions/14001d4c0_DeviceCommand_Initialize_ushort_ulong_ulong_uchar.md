# DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)

- ea: `0x14001d4c0`
- end: `0x14001d680`
- name: `?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z`
- size: `448`
- prototype: `__int64 __fastcall(DeviceCommand *__hidden this, unsigned __int16, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `31`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400123c0`
- `0x140012610`
- `0x14004f700`
- `0x140050318`
- `0x140061750`
- `0x140063764`
- `0x14006b040`
- `0x14006b410`
- `0x14006de00`
- `0x14006df5c`
- `0x140071820`
- `0x140071c10`
- `0x140075fb0`
- `0x14007b9a0`
- `0x14007bbd0`
- `0x14007f07c`
- `0x14007f3bc`
- `0x140081588`
- `0x1400871a0`
- `0x140091710`
- `0x14009292c`
- `0x1400ad300`
- `0x1400b1d28`
- `0x1400b511c`
- `0x1400b5d00`
- `0x1400ba93c`
- `0x1400bad7c`
- `0x1400bbed4`
- `0x1400be3c0`
- `0x1400c1f50`
- `0x1400c5aa0`

## callees

- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`

## pseudocode

```c
__int64 __fastcall DeviceCommand::Initialize(
        DeviceCommand *this,
        __int16 a2,
        int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  __int16 v6; // bp
  unsigned int v9; // ebx
  signed __int32 v10; // eax
  unsigned int v12; // [rsp+38h] [rbp-20h]

  v6 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      10,
      (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
      (char)this,
      *((_DWORD *)this + 2));
  }
  if ( a3 && a5 && a4 >= 0x30 )
  {
    v9 = 0;
    *((_WORD *)this + 82) = v6;
    *((_DWORD *)this + 24) = a3;
    v10 = _InterlockedIncrement(&s_NextCommandToken);
    if ( !v10 )
      v10 = _InterlockedIncrement(&s_NextCommandToken);
    *((_DWORD *)this + 40) = v10;
    *((_DWORD *)this + 32) = a4;
    *((_QWORD *)this + 17) = a5;
    *((_BYTE *)this + 167) = 1;
    *((_DWORD *)a5 + 2) &= 0xFFFFFFF8;
    *((_DWORD *)a5 + 3) = 1;
    *((_QWORD *)a5 + 3) = 0;
    *(_DWORD *)a5 = a3;
    *((_DWORD *)a5 + 1) = *((_DWORD *)this + 32) - 32;
    *((_DWORD *)a5 + 10) = *((_DWORD *)this + 40);
    *((_WORD *)a5 + 16) = *((_WORD *)this + 82);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        11,
        (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
        (char)this,
        *((_DWORD *)this + 2));
    }
    v9 = -1073741811;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    v12 = v9;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      12,
      (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
      (char)this,
      *((_DWORD *)this + 2),
      v12);
  }
  return v9;
}

```

## disassembly

```asm
0x14001d4c0  push    r12
0x14001d4c2  push    r14
0x14001d4c4  sub     rsp, 48h
0x14001d4c8  mov     [rsp+58h+arg_8], rbp
0x14001d4cd  mov     r14, rcx
0x14001d4d0  mov     [rsp+58h+arg_10], rsi
0x14001d4d5  movzx   ebp, dx
0x14001d4d8  mov     [rsp+58h+arg_18], rdi
0x14001d4dd  mov     esi, r9d
0x14001d4e0  mov     [rsp+58h+var_18], r15
0x14001d4e5  mov     edi, r8d
0x14001d4e8  lea     r15, WPP_RECORDER_INITIALIZED
0x14001d4ef  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001d4f6  lea     r12, WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids
0x14001d4fd  jz      short loc_14001D536
0x14001d4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d506  cmp     byte ptr [rcx+29h], 5
0x14001d50a  jnb     short loc_14001D513
0x14001d50c  cmp     word ptr [rcx+48h], 0
0x14001d511  jz      short loc_14001D536
0x14001d513  mov     eax, [r14+8]
0x14001d517  mov     r9d, 0Ah
0x14001d51d  mov     rcx, [rcx+40h]
0x14001d521  mov     dl, 5
0x14001d523  mov     [rsp+58h+var_28], eax
0x14001d527  mov     [rsp+58h+var_30], r14
0x14001d52c  mov     [rsp+58h+var_38], r12
0x14001d531  call    WPP_RECORDER_SF_qD
0x14001d536  mov     [rsp+58h+arg_0], rbx
0x14001d53b  test    edi, edi
0x14001d53d  jz      loc_14001D5DF
0x14001d543  mov     rcx, [rsp+58h+arg_20]
0x14001d54b  test    rcx, rcx
0x14001d54e  jz      loc_14001D5DF
0x14001d554  cmp     esi, 30h ; '0'
0x14001d557  jb      loc_14001D5DF
0x14001d55d  xor     ebx, ebx
0x14001d55f  mov     [r14+0A4h], bp
0x14001d567  mov     [r14+60h], edi
0x14001d56b  mov     eax, 1
0x14001d570  lock xadd cs:?s_NextCommandToken@@3JA, eax; long s_NextCommandToken
0x14001d578  add     eax, 1
0x14001d57b  jnz     short loc_14001D58C
0x14001d57d  mov     eax, 1
0x14001d582  lock xadd cs:?s_NextCommandToken@@3JA, eax; long s_NextCommandToken
0x14001d58a  inc     eax
0x14001d58c  mov     [r14+0A0h], eax
0x14001d593  mov     [r14+80h], esi
0x14001d59a  mov     [r14+88h], rcx
0x14001d5a1  mov     byte ptr [r14+0A7h], 1
0x14001d5a9  and     dword ptr [rcx+8], 0FFFFFFF8h
0x14001d5ad  mov     dword ptr [rcx+0Ch], 1
0x14001d5b4  mov     [rcx+18h], rbx
0x14001d5b8  mov     [rcx], edi
0x14001d5ba  mov     eax, [r14+80h]
0x14001d5c1  sub     eax, 20h ; ' '
0x14001d5c4  mov     [rcx+4], eax
0x14001d5c7  mov     eax, [r14+0A0h]
0x14001d5ce  mov     [rcx+28h], eax
0x14001d5d1  movzx   eax, word ptr [r14+0A4h]
0x14001d5d9  mov     [rcx+20h], ax
0x14001d5dd  jmp     short loc_14001D617
0x14001d5df  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001d5e6  jz      short loc_14001D612
0x14001d5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5ef  mov     r9d, 0Bh
0x14001d5f5  mov     eax, [r14+8]
0x14001d5f9  mov     dl, 2
0x14001d5fb  mov     [rsp+58h+var_28], eax
0x14001d5ff  mov     [rsp+58h+var_30], r14
0x14001d604  mov     rcx, [rcx+40h]
0x14001d608  mov     [rsp+58h+var_38], r12
0x14001d60d  call    WPP_RECORDER_SF_qD
0x14001d612  mov     ebx, 0C000000Dh
0x14001d617  mov     rdi, [rsp+58h+arg_18]
0x14001d61c  mov     rsi, [rsp+58h+arg_10]
0x14001d621  mov     rbp, [rsp+58h+arg_8]
0x14001d626  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001d62d  mov     r15, [rsp+58h+var_18]
0x14001d632  jz      short loc_14001D66F
0x14001d634  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d63b  cmp     byte ptr [rcx+29h], 5
0x14001d63f  jnb     short loc_14001D648
0x14001d641  cmp     word ptr [rcx+48h], 0
0x14001d646  jz      short loc_14001D66F
0x14001d648  mov     eax, [r14+8]
0x14001d64c  mov     r9d, 0Ch
0x14001d652  mov     rcx, [rcx+40h]
0x14001d656  mov     dl, 5
0x14001d658  mov     [rsp+58h+var_20], ebx
0x14001d65c  mov     [rsp+58h+var_28], eax
0x14001d660  mov     [rsp+58h+var_30], r14
0x14001d665  mov     [rsp+58h+var_38], r12
0x14001d66a  call    WPP_RECORDER_SF_qDD
0x14001d66f  mov     eax, ebx
0x14001d671  mov     rbx, [rsp+58h+arg_0]
0x14001d676  add     rsp, 48h
0x14001d67a  pop     r14
0x14001d67c  pop     r12
0x14001d67e  retn
```
