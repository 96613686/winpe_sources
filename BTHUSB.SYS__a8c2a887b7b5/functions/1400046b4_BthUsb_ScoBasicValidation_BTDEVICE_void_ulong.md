# BthUsb_ScoBasicValidation(_BTDEVICE *,void *,ulong)

- ea: `0x1400046b4`
- end: `0x14000479d`
- name: `?BthUsb_ScoBasicValidation@@YAJPEAU_BTDEVICE@@PEAXK@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _BTDEVICE *, void *, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140004840`
- `0x140005180`
- `0x140019b00`
- `0x140019f30`

## callees

- `0x14000175c`
- `0x1400046b4`
- `0x140006db0`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoBasicValidation(struct _BTDEVICE *a1, int *a2, int a3)
{
  unsigned int v4; // ebx
  int v5; // r8d

  v4 = -1073741811;
  if ( a1 && a1->MiniportContext && a2 )
  {
    v5 = *a2;
    if ( *a2 == a3 )
    {
      if ( *((int *)a1->MiniportContext + 58) >= 0 )
      {
        return 0;
      }
      else
      {
        LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)a2,
          v5,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          35,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        return (unsigned int)-1073741637;
      }
    }
    else
    {
      LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)a2,
        v5,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        34,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
        a3,
        v5);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400046b4  push    rbx
0x1400046b6  sub     rsp, 50h
0x1400046ba  mov     r9d, r8d
0x1400046bd  mov     ebx, 0C000000Dh
0x1400046c2  test    rcx, rcx
0x1400046c5  jz      loc_140004794
0x1400046cb  mov     rax, [rcx]
0x1400046ce  test    rax, rax
0x1400046d1  jz      loc_140004794
0x1400046d7  test    rdx, rdx
0x1400046da  jz      loc_140004794
0x1400046e0  mov     r8d, [rdx]
0x1400046e3  cmp     r8d, r9d
0x1400046e6  jz      short loc_14000473B
0x1400046e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046ef  mov     eax, [rcx+2Ch]
0x1400046f2  test    al, 8
0x1400046f4  jz      short loc_140004700
0x1400046f6  cmp     byte ptr [rcx+29h], 2
0x1400046fa  jb      short loc_140004700
0x1400046fc  mov     dl, 1
0x1400046fe  jmp     short loc_140004702
0x140004700  xor     dl, dl
0x140004702  mov     [rsp+58h+var_10], r8d
0x140004707  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000470e  mov     [rsp+58h+var_18], r9d
0x140004713  mov     r9, [rcx+40h]
0x140004717  mov     rcx, [rcx+18h]
0x14000471b  mov     [rsp+58h+var_20], rax
0x140004720  mov     [rsp+58h+var_28], 22h ; '"'
0x140004727  mov     [rsp+58h+var_30], 4
0x14000472f  mov     [rsp+58h+var_38], 2
0x140004734  call    WPP_RECORDER_AND_TRACE_SF_dd
0x140004739  jmp     short loc_140004794
0x14000473b  cmp     dword ptr [rax+0E8h], 0
0x140004742  jge     short loc_140004792
0x140004744  mov     rcx, cs:WPP_GLOBAL_Control
0x14000474b  mov     eax, [rcx+2Ch]
0x14000474e  test    al, 8
0x140004750  jz      short loc_14000475C
0x140004752  cmp     byte ptr [rcx+29h], 2
0x140004756  jb      short loc_14000475C
0x140004758  mov     dl, 1
0x14000475a  jmp     short loc_14000475E
0x14000475c  xor     dl, dl
0x14000475e  mov     r9, [rcx+40h]
0x140004762  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140004769  mov     rcx, [rcx+18h]
0x14000476d  mov     [rsp+58h+var_20], rax
0x140004772  mov     [rsp+58h+var_28], 23h ; '#'
0x140004779  mov     [rsp+58h+var_30], 4
0x140004781  mov     [rsp+58h+var_38], 2
0x140004786  call    WPP_RECORDER_AND_TRACE_SF_
0x14000478b  mov     ebx, 0C00000BBh
0x140004790  jmp     short loc_140004794
0x140004792  xor     ebx, ebx
0x140004794  mov     eax, ebx
0x140004796  add     rsp, 50h
0x14000479a  pop     rbx
0x14000479b  retn
```
