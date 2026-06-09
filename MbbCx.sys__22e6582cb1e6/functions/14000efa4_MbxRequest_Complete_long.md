# MbxRequest::Complete(long)

- ea: `0x14000efa4`
- end: `0x14000f0b7`
- name: `?Complete@MbxRequest@@QEAAXJ@Z`
- size: `275`
- prototype: `void(MbxRequest *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f300`
- `0x14000f370`

## callees

- `0x1400051ac`
- `0x14000efa4`
- `0x14001b818`
- `0x14001ffa4`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f055`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f055`

## pseudocode

```c
void __fastcall MbxRequest::Complete(MbxRequest *this, int a2)
{
  int v4; // edx
  void *v5; // rcx
  int v6; // eax
  int v7; // eax
  _DWORD *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
    WdfDriverGlobals,
    *((_QWORD *)this + 3),
    off_14005DF70);
  v6 = *((_DWORD *)this + 11);
  if ( v6 != 1 )
  {
    if ( v6 == 2 )
    {
      v9 = *((_QWORD *)this + 4);
      v10 = *((_QWORD *)this + 10);
      *(_DWORD *)(v9 + 696) = a2;
      *(_DWORD *)(v9 + 660) = v10;
      goto LABEL_13;
    }
LABEL_14:
    __int2c();
    return;
  }
  v7 = *((_DWORD *)this + 10);
  if ( v7 == 3 )
  {
    MbbUtilSendMessageFragmentComplete(v5, *((_QWORD **)this + 6), a2);
    return;
  }
  if ( v7 != 4 )
  {
    if ( (unsigned int)(v7 - 1) <= 1 )
    {
      v9 = *((_QWORD *)this + 4);
      *(_DWORD *)(v9 + 640) = a2;
LABEL_13:
      MbxQueueMessage(*(_QWORD *)(v9 + 48), 2, v9);
      return;
    }
    goto LABEL_14;
  }
  v8 = (_DWORD *)*((_QWORD *)this + 6);
  if ( a2 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      9,
      23,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
      v8[2],
      v8[3]);
  }
  ExFreePoolWithTag(v8, 0);
}

```

## disassembly

```asm
0x14000efa4  mov     [rsp+arg_0], rbx
0x14000efa9  push    rdi
0x14000efaa  sub     rsp, 40h
0x14000efae  mov     rax, cs:WdfFunctions_01031
0x14000efb5  mov     rbx, rcx
0x14000efb8  mov     r8, cs:off_14005DF70
0x14000efbf  mov     edi, edx
0x14000efc1  mov     rdx, [rcx+18h]
0x14000efc5  mov     rax, [rax+650h]
0x14000efcc  mov     rcx, cs:WdfDriverGlobals
0x14000efd3  call    _guard_dispatch_icall
0x14000efd8  mov     eax, [rbx+2Ch]
0x14000efdb  cmp     eax, 1
0x14000efde  jnz     loc_14000F07A
0x14000efe4  mov     eax, [rbx+28h]
0x14000efe7  cmp     eax, 3
0x14000efea  jnz     short loc_14000EFFD
0x14000efec  mov     rdx, [rbx+30h]; void *
0x14000eff0  mov     r8d, edi; int
0x14000eff3  call    ?MbbUtilSendMessageFragmentComplete@@YAXPEAX0J@Z; MbbUtilSendMessageFragmentComplete(void *,void *,long)
0x14000eff8  jmp     loc_14000F0AB
0x14000effd  cmp     eax, 4
0x14000f000  jnz     short loc_14000F063
0x14000f002  mov     rbx, [rbx+30h]
0x14000f006  test    edi, edi
0x14000f008  jns     short loc_14000F050
0x14000f00a  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f011  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f018  jz      short loc_14000F050
0x14000f01a  mov     eax, [rbx+0Ch]
0x14000f01d  mov     r9d, 17h
0x14000f023  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f02a  mov     dl, 2
0x14000f02c  mov     [rsp+48h+var_18], eax
0x14000f030  mov     eax, [rbx+8]
0x14000f033  mov     [rsp+48h+var_20], eax
0x14000f037  lea     r8d, [r9-0Eh]
0x14000f03b  mov     rcx, [rcx+40h]
0x14000f03f  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14000f046  mov     [rsp+48h+var_28], rax
0x14000f04b  call    WPP_RECORDER_SF_DD
0x14000f050  xor     edx, edx; Tag
0x14000f052  mov     rcx, rbx; P
0x14000f055  call    cs:__imp_ExFreePoolWithTag
0x14000f05c  nop     dword ptr [rax+rax+00h]
0x14000f061  jmp     short loc_14000F0AB
0x14000f063  dec     eax
0x14000f065  cmp     eax, 1
0x14000f068  jbe     short loc_14000F06E
0x14000f06a  int     2Ch; Windows NT - assertion failure
0x14000f06c  jmp     short loc_14000F0AB
0x14000f06e  mov     rcx, [rbx+20h]
0x14000f072  mov     [rcx+280h], edi
0x14000f078  jmp     short loc_14000F093
0x14000f07a  cmp     eax, 2
0x14000f07d  jnz     short loc_14000F0A9
0x14000f07f  mov     rcx, [rbx+20h]
0x14000f083  mov     rax, [rbx+50h]
0x14000f087  mov     [rcx+2B8h], edi
0x14000f08d  mov     [rcx+294h], eax
0x14000f093  mov     r8, rcx
0x14000f096  mov     r9, rdi
0x14000f099  mov     rcx, [rcx+30h]
0x14000f09d  mov     edx, 2
0x14000f0a2  call    ?MbxQueueMessage@@YAHPEAU_MBB_REQUEST_MANAGER@@W4MBX_MESSAGE@@PEAX2@Z; MbxQueueMessage(_MBB_REQUEST_MANAGER *,MBX_MESSAGE,void *,void *)
0x14000f0a7  jmp     short loc_14000F0AB
0x14000f0a9  int     2Ch; Windows NT - assertion failure
0x14000f0ab  mov     rbx, [rsp+48h+arg_0]
0x14000f0b0  add     rsp, 40h
0x14000f0b4  pop     rdi
0x14000f0b5  retn
```
