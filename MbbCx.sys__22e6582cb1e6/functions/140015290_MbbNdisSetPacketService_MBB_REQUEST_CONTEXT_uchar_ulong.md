# MbbNdisSetPacketService(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140015290`
- end: `0x140015394`
- name: `?MbbNdisSetPacketService@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `260`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140015290`
- `0x1400208bc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400152b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400152b5`

## pseudocode

```c
__int64 __fastcall MbbNdisSetPacketService(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 Pool2; // rax
  unsigned __int8 *v6; // rdx
  int v8; // ecx
  int v9; // eax

  *a3 = 8;
  Pool2 = ExAllocatePool2(64, 4, 1683505741);
  v6 = (unsigned __int8 *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v6,
        3,
        99,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4));
    }
    return 3221225626LL;
  }
  *((_QWORD *)a1 + 70) = Pool2;
  v8 = *((_DWORD *)a2 + 1);
  if ( !v8 )
  {
    v9 = 0;
    goto LABEL_12;
  }
  if ( v8 == 1 )
  {
    v9 = 1;
LABEL_12:
    *(_DWORD *)v6 = v9;
    return MbbUtilSetAttributeWithParameter(a1, v6, 4u);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      3,
      100,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
      *((_DWORD *)a1 + 4),
      21);
  }
  return 3221291029LL;
}

```

## disassembly

```asm
0x140015290  mov     [rsp+arg_0], rbx
0x140015295  push    rdi
0x140015296  sub     rsp, 40h
0x14001529a  mov     rdi, rdx
0x14001529d  mov     dword ptr [r8], 8
0x1400152a4  mov     edx, 4
0x1400152a9  mov     rbx, rcx
0x1400152ac  mov     r8d, 6458424Dh
0x1400152b2  lea     ecx, [rdx+3Ch]
0x1400152b5  call    cs:__imp_ExAllocatePool2
0x1400152bc  nop     dword ptr [rax+rax+00h]
0x1400152c1  mov     rdx, rax; unsigned __int8 *
0x1400152c4  test    rax, rax
0x1400152c7  jnz     short loc_14001530D
0x1400152c9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400152d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400152d7  jz      short loc_140015306
0x1400152d9  mov     eax, [rbx+10h]
0x1400152dc  lea     r9d, [rdx+63h]
0x1400152e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400152e7  lea     r8d, [rdx+3]
0x1400152eb  mov     [rsp+48h+var_20], eax
0x1400152ef  mov     dl, 2
0x1400152f1  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400152f8  mov     [rsp+48h+var_28], rax
0x1400152fd  mov     rcx, [rcx+40h]
0x140015301  call    WPP_RECORDER_SF_d
0x140015306  mov     eax, 0C000009Ah
0x14001530b  jmp     short loc_140015388
0x14001530d  mov     [rbx+230h], rdx
0x140015314  mov     ecx, [rdi+4]
0x140015317  test    ecx, ecx
0x140015319  jz      short loc_140015373
0x14001531b  cmp     ecx, 1
0x14001531e  jz      short loc_14001536C
0x140015320  lea     rax, WPP_RECORDER_INITIALIZED
0x140015327  mov     edi, 0C0010015h
0x14001532c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015333  jz      short loc_140015368
0x140015335  mov     ecx, [rbx+10h]
0x140015338  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001533f  mov     [rsp+48h+var_18], edi
0x140015343  mov     r9d, 64h ; 'd'
0x140015349  mov     [rsp+48h+var_20], ecx
0x14001534d  mov     dl, 2
0x14001534f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015356  mov     [rsp+48h+var_28], rax
0x14001535b  lea     r8d, [r9-61h]
0x14001535f  mov     rcx, [rcx+40h]
0x140015363  call    WPP_RECORDER_SF_DD
0x140015368  mov     eax, edi
0x14001536a  jmp     short loc_140015388
0x14001536c  mov     eax, 1
0x140015371  jmp     short loc_140015375
0x140015373  xor     eax, eax
0x140015375  mov     rcx, rdx
0x140015378  mov     [rdx], eax
0x14001537a  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14001537d  mov     r8d, 4; unsigned int
0x140015383  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140015388  mov     rbx, [rsp+48h+arg_0]
0x14001538d  add     rsp, 40h
0x140015391  pop     rdi
0x140015392  retn
```
