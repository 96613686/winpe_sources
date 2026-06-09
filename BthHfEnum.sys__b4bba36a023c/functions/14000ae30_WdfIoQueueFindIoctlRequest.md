# WdfIoQueueFindIoctlRequest

- ea: `0x14000ae30`
- end: `0x14000aff4`
- name: `WdfIoQueueFindIoctlRequest`
- size: `452`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a914`
- `0x14000aac0`
- `0x14000b0ac`
- `0x14002c41c`

## callees

- `0x14000ae30`
- `0x14001adc0`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall WdfIoQueueFindIoctlRequest(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  __int64 v8; // rbx
  int v9; // esi
  int v10; // ebx
  __int64 result; // rax
  __int64 i; // [rsp+40h] [rbp-40h] BYREF
  __int128 v13; // [rsp+48h] [rbp-38h] BYREF
  __int128 v14; // [rsp+58h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-18h]

  if ( a4 )
    *a4 = 0;
LABEL_3:
  while ( 2 )
  {
    v8 = 0;
    for ( i = 0; ; v8 = i )
    {
      v15 = 0;
      v13 = 0;
      LOWORD(v13) = 40;
      v14 = 0;
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, __int128 *, __int64 *))(WdfFunctions_01015 + 1280))(
             WdfDriverGlobals,
             a1,
             v8,
             a2,
             &v13,
             &i);
      if ( v8 )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
          WdfDriverGlobals,
          v8,
          0,
          220,
          "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthintioctl.cpp");
      if ( v9 == -2147483622 )
        return 3221225473LL;
      if ( v9 == -1073741275 )
        goto LABEL_3;
      if ( v9 < 0 )
        return 3221225473LL;
      if ( a3 == DWORD2(v14) )
        break;
    }
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD *))(WdfFunctions_01015 + 1288))(
              WdfDriverGlobals,
              a1,
              i,
              a4);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
        WdfDriverGlobals,
        i,
        0,
        262,
        "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthintioctl.cpp");
      if ( v10 == -1073741275 )
        continue;
      result = 0;
      if ( v10 < 0 )
        return 3221225473LL;
    }
    else
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
        WdfDriverGlobals,
        i,
        0,
        250,
        "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthintioctl.cpp");
      return 0;
    }
    return result;
  }
}

```

## disassembly

```asm
0x14000ae30  push    rbp
0x14000ae32  push    rbx
0x14000ae33  push    rsi
0x14000ae34  push    rdi
0x14000ae35  push    r12
0x14000ae37  push    r14
0x14000ae39  push    r15
0x14000ae3b  mov     rbp, rsp
0x14000ae3e  sub     rsp, 80h
0x14000ae45  mov     rax, cs:__security_cookie
0x14000ae4c  xor     rax, rsp
0x14000ae4f  mov     [rbp+var_10], rax
0x14000ae53  mov     rdi, r9
0x14000ae56  mov     r14d, r8d
0x14000ae59  mov     r12, rdx
0x14000ae5c  mov     r15, rcx
0x14000ae5f  test    r9, r9
0x14000ae62  jz      short loc_14000AE6B
0x14000ae64  mov     qword ptr [r9], 0
0x14000ae6b  xor     ebx, ebx
0x14000ae6d  mov     [rbp+var_40], rbx
0x14000ae71  xor     eax, eax
0x14000ae73  lea     rcx, [rbp+var_40]
0x14000ae77  mov     [rbp+var_18], rax
0x14000ae7b  xorps   xmm0, xmm0
0x14000ae7e  mov     [rsp+80h+var_58], rcx
0x14000ae83  mov     eax, 28h ; '('
0x14000ae88  movups  [rbp+var_38], xmm0
0x14000ae8c  mov     word ptr [rbp+var_38], ax
0x14000ae90  lea     rcx, [rbp+var_38]
0x14000ae94  mov     rax, cs:WdfFunctions_01015
0x14000ae9b  mov     r9, r12
0x14000ae9e  movups  [rbp+var_28], xmm0
0x14000aea2  mov     [rsp+80h+var_60], rcx
0x14000aea7  mov     r8, rbx
0x14000aeaa  mov     rcx, cs:WdfDriverGlobals
0x14000aeb1  mov     rdx, r15
0x14000aeb4  mov     rax, [rax+500h]
0x14000aebb  call    _guard_dispatch_icall
0x14000aec0  mov     esi, eax
0x14000aec2  test    rbx, rbx
0x14000aec5  jz      short loc_14000AEF9
0x14000aec7  mov     rcx, cs:WdfFunctions_01015
0x14000aece  mov     r9d, 0DCh
0x14000aed4  xor     r8d, r8d
0x14000aed7  mov     rdx, rbx
0x14000aeda  mov     rax, [rcx+670h]
0x14000aee1  lea     rcx, aOnecoreuapDriv_0; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000aee8  mov     [rsp+80h+var_60], rcx
0x14000aeed  mov     rcx, cs:WdfDriverGlobals
0x14000aef4  call    _guard_dispatch_icall
0x14000aef9  cmp     esi, 8000001Ah
0x14000aeff  jz      loc_14000AFD0
0x14000af05  cmp     esi, 0C0000225h
0x14000af0b  jz      loc_14000AE6B
0x14000af11  test    esi, esi
0x14000af13  js      loc_14000AFD0
0x14000af19  cmp     r14d, dword ptr [rbp+var_28+8]
0x14000af1d  jnz     short loc_14000AF97
0x14000af1f  mov     rax, cs:WdfFunctions_01015
0x14000af26  test    rdi, rdi
0x14000af29  jz      short loc_14000AFA0
0x14000af2b  mov     rax, [rax+508h]
0x14000af32  mov     r9, rdi
0x14000af35  mov     r8, [rbp+var_40]
0x14000af39  mov     rdx, r15
0x14000af3c  mov     rcx, cs:WdfDriverGlobals
0x14000af43  call    _guard_dispatch_icall
0x14000af48  mov     rcx, cs:WdfFunctions_01015
0x14000af4f  mov     ebx, eax
0x14000af51  mov     rdx, [rbp+var_40]
0x14000af55  mov     r9d, 106h
0x14000af5b  xor     r8d, r8d
0x14000af5e  mov     rax, [rcx+670h]
0x14000af65  lea     rcx, aOnecoreuapDriv_0; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000af6c  mov     [rsp+80h+var_60], rcx
0x14000af71  mov     rcx, cs:WdfDriverGlobals
0x14000af78  call    _guard_dispatch_icall
0x14000af7d  cmp     ebx, 0C0000225h
0x14000af83  jz      loc_14000AE6B
0x14000af89  xor     eax, eax
0x14000af8b  mov     ecx, 0C0000001h
0x14000af90  test    ebx, ebx
0x14000af92  cmovs   eax, ecx
0x14000af95  jmp     short loc_14000AFD5
0x14000af97  mov     rbx, [rbp+var_40]
0x14000af9b  jmp     loc_14000AE71
0x14000afa0  mov     rax, [rax+670h]
0x14000afa7  lea     rcx, aOnecoreuapDriv_0; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000afae  mov     rdx, [rbp+var_40]
0x14000afb2  mov     r9d, 0FAh
0x14000afb8  mov     [rsp+80h+var_60], rcx
0x14000afbd  xor     r8d, r8d
0x14000afc0  mov     rcx, cs:WdfDriverGlobals
0x14000afc7  call    _guard_dispatch_icall
0x14000afcc  xor     eax, eax
0x14000afce  jmp     short loc_14000AFD5
0x14000afd0  mov     eax, 0C0000001h
0x14000afd5  mov     rcx, [rbp+var_10]
0x14000afd9  xor     rcx, rsp; StackCookie
0x14000afdc  call    __security_check_cookie
0x14000afe1  add     rsp, 80h
0x14000afe8  pop     r15
0x14000afea  pop     r14
0x14000afec  pop     r12
0x14000afee  pop     rdi
0x14000afef  pop     rsi
0x14000aff0  pop     rbx
0x14000aff1  pop     rbp
0x14000aff2  retn
```
