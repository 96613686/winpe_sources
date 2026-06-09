# MbbNdisSetServiceActivation(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140016200`
- end: `0x14001635d`
- name: `?MbbNdisSetServiceActivation@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `349`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140016200`
- `0x1400208bc`
- `0x140048040`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400162d5`
- `ntoskrnl!ExAllocatePool2` at `0x1400162d5`

## pseudocode

```c
__int64 __fastcall MbbNdisSetServiceActivation(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  unsigned __int8 *v3; // r14
  size_t v4; // rbx
  unsigned __int8 *Pool2; // rax
  int v8; // edx
  unsigned __int8 *v9; // rbp

  *a3 = 8;
  v3 = a2;
  v4 = *((unsigned int *)a2 + 1);
  if ( (unsigned int)v4 <= 0x10000 )
  {
    if ( *((_DWORD *)a2 + 1) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          3,
          117,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4),
          v4);
      }
      return 3221291030LL;
    }
    else
    {
      Pool2 = (unsigned __int8 *)ExAllocatePool2(64, *((unsigned int *)a2 + 1), 1683505741);
      v9 = Pool2;
      if ( Pool2 )
      {
        *((_QWORD *)a1 + 70) = Pool2;
        memmove(Pool2, v3 + 8, v4);
        return MbbUtilSetAttributeWithParameter(a1, v9, v4);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v8) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            3,
            118,
            (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
            *((_DWORD *)a1 + 4));
        }
        return 3221225626LL;
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        3,
        116,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4),
        v4);
    }
    return 3221291028LL;
  }
}

```

## disassembly

```asm
0x140016200  push    rbx
0x140016202  push    rbp
0x140016203  push    rsi
0x140016204  push    rdi
0x140016205  push    r14
0x140016207  sub     rsp, 40h
0x14001620b  mov     dword ptr [r8], 8
0x140016212  mov     r14, rdx
0x140016215  mov     ebx, [rdx+4]
0x140016218  mov     rsi, rcx
0x14001621b  cmp     ebx, 10000h
0x140016221  jbe     short loc_140016270
0x140016223  lea     rax, WPP_RECORDER_INITIALIZED
0x14001622a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140016231  jz      short loc_140016266
0x140016233  mov     eax, [rcx+10h]
0x140016236  mov     r9d, 74h ; 't'
0x14001623c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016243  mov     dl, 2
0x140016245  mov     [rsp+68h+var_38], ebx
0x140016249  mov     [rsp+68h+var_40], eax
0x14001624d  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140016254  lea     r8d, [r9-71h]
0x140016258  mov     [rsp+68h+var_48], rax
0x14001625d  mov     rcx, [rcx+40h]
0x140016261  call    WPP_RECORDER_SF_DD
0x140016266  mov     eax, 0C0010014h
0x14001626b  jmp     loc_140016351
0x140016270  lea     rax, [rbx+8]
0x140016274  cmp     rax, 8
0x140016278  jbe     short loc_1400162C7
0x14001627a  lea     rax, WPP_RECORDER_INITIALIZED
0x140016281  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140016288  jz      short loc_1400162BD
0x14001628a  mov     eax, [rcx+10h]
0x14001628d  mov     r9d, 75h ; 'u'
0x140016293  mov     rcx, cs:WPP_GLOBAL_Control
0x14001629a  mov     dl, 2
0x14001629c  mov     [rsp+68h+var_38], ebx
0x1400162a0  mov     [rsp+68h+var_40], eax
0x1400162a4  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400162ab  lea     r8d, [r9-72h]
0x1400162af  mov     [rsp+68h+var_48], rax
0x1400162b4  mov     rcx, [rcx+40h]
0x1400162b8  call    WPP_RECORDER_SF_DD
0x1400162bd  mov     eax, 0C0010016h
0x1400162c2  jmp     loc_140016351
0x1400162c7  mov     r8d, 6458424Dh
0x1400162cd  mov     rdx, rbx
0x1400162d0  mov     ecx, 40h ; '@'
0x1400162d5  call    cs:__imp_ExAllocatePool2
0x1400162dc  nop     dword ptr [rax+rax+00h]
0x1400162e1  mov     rbp, rax
0x1400162e4  test    rax, rax
0x1400162e7  jnz     short loc_14001632D
0x1400162e9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400162f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400162f7  jz      short loc_140016326
0x1400162f9  mov     eax, [rsi+10h]
0x1400162fc  lea     r9d, [rbp+76h]
0x140016300  mov     rcx, cs:WPP_GLOBAL_Control
0x140016307  lea     r8d, [rbp+3]
0x14001630b  mov     [rsp+68h+var_40], eax
0x14001630f  mov     dl, 2
0x140016311  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140016318  mov     [rsp+68h+var_48], rax
0x14001631d  mov     rcx, [rcx+40h]
0x140016321  call    WPP_RECORDER_SF_d
0x140016326  mov     eax, 0C000009Ah
0x14001632b  jmp     short loc_140016351
0x14001632d  lea     rdx, [r14+8]; Src
0x140016331  mov     [rsi+230h], rbp
0x140016338  mov     r8, rbx; Size
0x14001633b  mov     rcx, rbp; void *
0x14001633e  call    memmove
0x140016343  mov     r8d, ebx; unsigned int
0x140016346  mov     rdx, rbp; unsigned __int8 *
0x140016349  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x14001634c  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140016351  add     rsp, 40h
0x140016355  pop     r14
0x140016357  pop     rdi
0x140016358  pop     rsi
0x140016359  pop     rbp
0x14001635a  pop     rbx
0x14001635b  retn
```
