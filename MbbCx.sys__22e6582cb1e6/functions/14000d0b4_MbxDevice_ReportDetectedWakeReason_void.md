# MbxDevice::ReportDetectedWakeReason(void)

- ea: `0x14000d0b4`
- end: `0x14000d3c8`
- name: `?ReportDetectedWakeReason@MbxDevice@@AEAAXXZ`
- size: `788`
- prototype: `void __fastcall(MbxDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a0a8`

## callees

- `0x14000d0b4`
- `0x14000dc54`
- `0x14000e3b4`
- `0x14000e6d8`
- `0x14003e100`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000d0df`
- `ntoskrnl!RtlCompareMemory` at `0x14000d219`
- `ntoskrnl!RtlCompareMemory` at `0x14000d29a`
- `ntoskrnl!RtlCompareMemory` at `0x14000d0df`
- `ntoskrnl!RtlCompareMemory` at `0x14000d219`
- `ntoskrnl!RtlCompareMemory` at `0x14000d29a`

## pseudocode

```c
void __fastcall MbxDevice::ReportDetectedWakeReason(MbxDevice *this)
{
  char *v1; // rsi
  int v3; // edx
  int v4; // r8d
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  int v8; // r9d
  int v9; // edx
  int v10; // r8d
  int v11; // r9d

  v1 = (char *)this + 1559;
  if ( RtlCompareMemory((char *)this + 1559, &MBB_UUID_BASIC_CONNECT, 0x10u) != 16 )
  {
    if ( RtlCompareMemory(v1, &MBB_UUID_SMS, 0x10u) == 16 )
    {
      if ( *((_DWORD *)v1 + 4) == 5 )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 419);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v8 = 143;
        goto LABEL_32;
      }
      _InterlockedIncrement((volatile signed __int32 *)this + 425);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      MbbUtilGetCommandString((struct _MBB_COMMAND *)v1);
      v7 = 144;
    }
    else
    {
      if ( RtlCompareMemory(v1, &MBB_UUID_USSD, 0x10u) != 16 )
      {
        if ( !*(_OWORD *)v1 )
        {
          _InterlockedIncrement((volatile signed __int32 *)this + 424);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return;
          v8 = 147;
          goto LABEL_32;
        }
        _InterlockedIncrement((volatile signed __int32 *)this + 425);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          MbbUtilGetCommandString((struct _MBB_COMMAND *)v1);
          WPP_RECORDER_SF__guid_sdl(WPP_GLOBAL_Control->DeviceExtension, v9, v10, v11);
        }
        return;
      }
      if ( *((_DWORD *)v1 + 4) == 1 )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 420);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v8 = 145;
        goto LABEL_32;
      }
      _InterlockedIncrement((volatile signed __int32 *)this + 425);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      MbbUtilGetCommandString((struct _MBB_COMMAND *)v1);
      v7 = 146;
    }
LABEL_8:
    WPP_RECORDER_SF_sdl(WPP_GLOBAL_Control->DeviceExtension, v5, v6, v7);
    return;
  }
  switch ( *((_DWORD *)v1 + 4) )
  {
    case 2:
      _InterlockedIncrement((volatile signed __int32 *)this + 422);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v8 = 141;
      goto LABEL_32;
    case 9:
      _InterlockedIncrement((volatile signed __int32 *)this + 418);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v8 = 139;
      goto LABEL_32;
    case 0xA:
      _InterlockedIncrement((volatile signed __int32 *)this + 421);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v8 = 140;
      goto LABEL_32;
  }
  if ( *((_DWORD *)v1 + 4) != 12 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 425);
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    MbbUtilGetCommandString((struct _MBB_COMMAND *)v1);
    v7 = 142;
    goto LABEL_8;
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 423);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = 138;
LABEL_32:
    WPP_RECORDER_SF_l(WPP_GLOBAL_Control->DeviceExtension, v3, v4, v8);
  }
}

```

## disassembly

```asm
0x14000d0b4  mov     [rsp+arg_0], rbx
0x14000d0b9  mov     [rsp+arg_8], rsi
0x14000d0be  push    rdi
0x14000d0bf  sub     rsp, 60h
0x14000d0c3  lea     rsi, [rcx+617h]
0x14000d0ca  mov     rdi, rcx
0x14000d0cd  mov     ebx, 10h
0x14000d0d2  lea     rdx, MBB_UUID_BASIC_CONNECT; Source2
0x14000d0d9  mov     r8d, ebx; Length
0x14000d0dc  mov     rcx, rsi; Source1
0x14000d0df  call    cs:__imp_RtlCompareMemory
0x14000d0e6  nop     dword ptr [rax+rax+00h]
0x14000d0eb  cmp     rax, rbx
0x14000d0ee  jnz     loc_14000D20C
0x14000d0f4  mov     ecx, [rsi+10h]
0x14000d0f7  sub     ecx, 2
0x14000d0fa  jz      loc_14000D1E0
0x14000d100  sub     ecx, 7
0x14000d103  jz      loc_14000D1BD
0x14000d109  sub     ecx, 1
0x14000d10c  jz      loc_14000D19A
0x14000d112  cmp     ecx, 2
0x14000d115  jz      short loc_14000D16E
0x14000d117  lock inc dword ptr [rdi+6A4h]
0x14000d11e  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d125  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d12c  jz      loc_14000D3B7
0x14000d132  mov     ebx, [rdi+6A4h]
0x14000d138  mov     rcx, rsi; Source1
0x14000d13b  mov     edi, [rdi+627h]
0x14000d141  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14000d146  mov     r9d, 8Eh
0x14000d14c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d153  mov     [rsp+68h+var_30], ebx
0x14000d157  mov     dword ptr [rsp+68h+var_38], edi
0x14000d15b  mov     [rsp+68h+var_40], rax
0x14000d160  mov     rcx, [rcx+40h]
0x14000d164  call    WPP_RECORDER_SF_sdl
0x14000d169  jmp     loc_14000D3B7
0x14000d16e  lock inc dword ptr [rdi+69Ch]
0x14000d175  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d17c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d183  jz      loc_14000D3B7
0x14000d189  mov     eax, [rdi+69Ch]
0x14000d18f  mov     r9d, 8Ah
0x14000d195  jmp     loc_14000D354
0x14000d19a  lock inc dword ptr [rdi+694h]
0x14000d1a1  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d1a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d1af  jz      loc_14000D3B7
0x14000d1b5  mov     r9d, 8Ch
0x14000d1bb  jmp     short loc_14000D201
0x14000d1bd  lock inc dword ptr [rdi+688h]
0x14000d1c4  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d1cb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d1d2  jz      loc_14000D3B7
0x14000d1d8  mov     r9d, 8Bh
0x14000d1de  jmp     short loc_14000D201
0x14000d1e0  lock inc dword ptr [rdi+698h]
0x14000d1e7  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d1ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d1f5  jz      loc_14000D3B7
0x14000d1fb  mov     r9d, 8Dh
0x14000d201  mov     eax, [rdi+688h]
0x14000d207  jmp     loc_14000D354
0x14000d20c  mov     r8, rbx; Length
0x14000d20f  lea     rdx, MBB_UUID_SMS; Source2
0x14000d216  mov     rcx, rsi; Source1
0x14000d219  call    cs:__imp_RtlCompareMemory
0x14000d220  nop     dword ptr [rax+rax+00h]
0x14000d225  cmp     rax, rbx
0x14000d228  jnz     short loc_14000D28D
0x14000d22a  cmp     dword ptr [rsi+10h], 5
0x14000d22e  jz      short loc_14000D26A
0x14000d230  lock inc dword ptr [rdi+6A4h]
0x14000d237  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d23e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d245  jz      loc_14000D3B7
0x14000d24b  mov     ebx, [rdi+6A4h]
0x14000d251  mov     rcx, rsi; Source1
0x14000d254  mov     edi, [rdi+627h]
0x14000d25a  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14000d25f  mov     r9d, 90h
0x14000d265  jmp     loc_14000D14C
0x14000d26a  lock inc dword ptr [rdi+68Ch]
0x14000d271  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d278  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d27f  jz      loc_14000D3B7
0x14000d285  mov     r9d, 8Fh
0x14000d28b  jmp     short loc_14000D30C
0x14000d28d  mov     r8, rbx; Length
0x14000d290  lea     rdx, MBB_UUID_USSD; Source2
0x14000d297  mov     rcx, rsi; Source1
0x14000d29a  call    cs:__imp_RtlCompareMemory
0x14000d2a1  nop     dword ptr [rax+rax+00h]
0x14000d2a6  cmp     rax, rbx
0x14000d2a9  jnz     short loc_14000D314
0x14000d2ab  cmp     dword ptr [rsi+10h], 1
0x14000d2af  jz      short loc_14000D2EB
0x14000d2b1  lock inc dword ptr [rdi+6A4h]
0x14000d2b8  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d2bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d2c6  jz      loc_14000D3B7
0x14000d2cc  mov     ebx, [rdi+6A4h]
0x14000d2d2  mov     rcx, rsi; Source1
0x14000d2d5  mov     edi, [rdi+627h]
0x14000d2db  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14000d2e0  mov     r9d, 92h
0x14000d2e6  jmp     loc_14000D14C
0x14000d2eb  lock inc dword ptr [rdi+690h]
0x14000d2f2  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d2f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d300  jz      loc_14000D3B7
0x14000d306  mov     r9d, 91h
0x14000d30c  mov     eax, [rdi+68Ch]
0x14000d312  jmp     short loc_14000D354
0x14000d314  xorps   xmm0, xmm0
0x14000d317  movq    rax, xmm0
0x14000d31c  movups  [rsp+68h+var_18], xmm0
0x14000d321  cmp     [rsi], rax
0x14000d324  jnz     short loc_14000D36A
0x14000d326  mov     rax, [rsi+8]
0x14000d32a  cmp     rax, qword ptr [rsp+68h+var_18+8]
0x14000d32f  jnz     short loc_14000D36A
0x14000d331  lock inc dword ptr [rdi+6A0h]
0x14000d338  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d33f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d346  jz      short loc_14000D3B7
0x14000d348  mov     eax, [rdi+6A0h]
0x14000d34e  mov     r9d, 93h
0x14000d354  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d35b  mov     dword ptr [rsp+68h+var_40], eax
0x14000d35f  mov     rcx, [rcx+40h]
0x14000d363  call    WPP_RECORDER_SF_l
0x14000d368  jmp     short loc_14000D3B7
0x14000d36a  lock inc dword ptr [rdi+6A4h]
0x14000d371  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d378  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d37f  jz      short loc_14000D3B7
0x14000d381  mov     ebx, [rdi+6A4h]
0x14000d387  mov     rcx, rsi; Source1
0x14000d38a  mov     edi, [rdi+627h]
0x14000d390  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14000d395  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d39c  mov     [rsp+68h+var_28], ebx
0x14000d3a0  mov     [rsp+68h+var_30], edi
0x14000d3a4  mov     [rsp+68h+var_38], rax
0x14000d3a9  mov     rcx, [rcx+40h]
0x14000d3ad  mov     [rsp+68h+var_40], rsi
0x14000d3b2  call    WPP_RECORDER_SF__guid_sdl
0x14000d3b7  mov     rbx, [rsp+68h+arg_0]
0x14000d3bc  mov     rsi, [rsp+68h+arg_8]
0x14000d3c1  add     rsp, 60h
0x14000d3c5  pop     rdi
0x14000d3c6  retn
```
