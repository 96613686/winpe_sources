# AuthHostWebInstance::UpdateZoomFromScaleFactor(void)

- ea: `0x140008450`
- end: `0x140008523`
- name: `?UpdateZoomFromScaleFactor@AuthHostWebInstance@@AEAAXXZ`
- size: `211`
- prototype: `void __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140005940`
- `0x140007e3c`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x140008450`
- `0x140014010`

## import_xrefs

- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x14000846b`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x14000846b`

## pseudocode

```c
void __fastcall AuthHostWebInstance::UpdateZoomFromScaleFactor(AuthHostWebInstance *this)
{
  int ScaleFactorForDevice; // eax
  __int64 v3; // rcx
  int v4; // eax
  __int128 v5; // [rsp+40h] [rbp-28h] BYREF
  __int64 v6; // [rsp+50h] [rbp-18h]

  v6 = 0;
  v5 = 0;
  ScaleFactorForDevice = GetScaleFactorForDevice(1);
  LOWORD(v5) = 3;
  v3 = *((_QWORD *)this + 10);
  DWORD2(v5) = ScaleFactorForDevice;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v3 + 32LL))(
         v3,
         0,
         63,
         1,
         &v5,
         0);
  if ( v4 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids, (unsigned int)v4);
  }
}

```

## disassembly

```asm
0x140008450  push    rbx
0x140008452  sub     rsp, 60h
0x140008456  xor     eax, eax
0x140008458  mov     rbx, rcx
0x14000845b  xorps   xmm0, xmm0
0x14000845e  mov     [rsp+68h+var_18], rax
0x140008463  movups  [rsp+68h+var_28], xmm0
0x140008468  lea     ecx, [rax+1]
0x14000846b  call    cs:__imp_GetScaleFactorForDevice
0x140008471  mov     ecx, 3
0x140008476  mov     [rsp+68h+var_40], 0
0x14000847f  mov     word ptr [rsp+68h+var_28], cx
0x140008484  lea     rdx, [rsp+68h+var_28]
0x140008489  mov     rcx, [rbx+50h]
0x14000848d  mov     dword ptr [rsp+68h+var_28+8], eax
0x140008491  mov     [rsp+68h+var_48], rdx
0x140008496  xor     edx, edx
0x140008498  mov     rax, [rcx]
0x14000849b  lea     r9d, [rdx+1]
0x14000849f  lea     r8d, [rdx+3Fh]
0x1400084a3  mov     rax, [rax+20h]
0x1400084a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084ac  test    eax, eax
0x1400084ae  jns     short loc_1400084E9
0x1400084b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084b7  lea     rdx, WPP_GLOBAL_Control
0x1400084be  cmp     rcx, rdx
0x1400084c1  jz      short loc_14000851D
0x1400084c3  test    byte ptr [rcx+44h], 2
0x1400084c7  jz      short loc_14000851D
0x1400084c9  cmp     byte ptr [rcx+41h], 2
0x1400084cd  jb      short loc_14000851D
0x1400084cf  mov     rcx, [rcx+38h]
0x1400084d3  lea     r8, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids
0x1400084da  mov     edx, 28h ; '('
0x1400084df  mov     r9d, eax
0x1400084e2  call    WPP_SF_d
0x1400084e7  jmp     short loc_14000851D
0x1400084e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084f0  lea     rdx, WPP_GLOBAL_Control
0x1400084f7  cmp     rcx, rdx
0x1400084fa  jz      short loc_14000851D
0x1400084fc  test    byte ptr [rcx+44h], 2
0x140008500  jz      short loc_14000851D
0x140008502  cmp     byte ptr [rcx+41h], 5
0x140008506  jb      short loc_14000851D
0x140008508  mov     rcx, [rcx+38h]
0x14000850c  lea     r8, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids
0x140008513  mov     edx, 29h ; ')'
0x140008518  call    WPP_SF_
0x14000851d  add     rsp, 60h
0x140008521  pop     rbx
0x140008522  retn
```
