# _CMidi2KSMidiEndpointManager::OnDeviceAdded_::_1_::_lambda_3_::operator()

- ea: `0x180018a08`
- end: `0x180018af1`
- name: `_CMidi2KSMidiEndpointManager::OnDeviceAdded_::_1_::_lambda_3_::operator()`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b7a0`

## callees

- `0x180004434`
- `0x18000a814`
- `0x180018a08`
- `0x18002741c`

## string_xrefs

- `0x180018a70`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`
- `0x180018aba`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2KSMidiEndpointManager::OnDeviceAdded_::_1_::_lambda_3_::operator()(__int64 a1, void *a2)
{
  unsigned int *v2; // r14
  void **v3; // r15
  _DWORD *v5; // rdx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rdx
  void *v10; // rcx
  unsigned int v11; // eax
  void *v12; // rbx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v16; // [rsp+50h] [rbp+8h] BYREF
  void *Block; // [rsp+60h] [rbp+18h] BYREF

  v2 = *(unsigned int **)(a1 + 16);
  v3 = *(void ***)(a1 + 8);
  v5 = *(_DWORD **)a1;
  Block = 0;
  LODWORD(v5) = *v5;
  v16 = 0;
  v6 = PinPropertyAllocate(a2, (int)v5, &GUID_8c134960_51ad_11cf_878a_94f801c10000, 3, &Block, &v16);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v11 = v16;
    if ( v16 >= 8 )
    {
      v12 = Block;
      if ( *((_DWORD *)Block + 1) )
      {
        *v3 = Block;
        v7 = 0;
        *v2 = v11;
        return v7;
      }
      v7 = -2147023266;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
        (const char *)0x8007065ELL,
        v14);
      v10 = v12;
      goto LABEL_4;
    }
    v7 = -2147023266;
    v9 = 344;
    v8 = 2147944030LL;
  }
  else
  {
    v8 = (unsigned int)v6;
    v9 = 342;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
    (const char *)v8,
    v14);
  v10 = Block;
  if ( Block )
LABEL_4:
    operator delete(v10);
  return v7;
}

```

## disassembly

```asm
0x180018a08  mov     r11, rsp
0x180018a0b  mov     [r11+10h], rbx
0x180018a0f  push    rdi
0x180018a10  push    r14
0x180018a12  push    r15
0x180018a14  sub     rsp, 30h
0x180018a18  mov     r14, [rcx+10h]
0x180018a1c  lea     r8, _GUID_8c134960_51ad_11cf_878a_94f801c10000; struct _GUID *
0x180018a23  mov     r15, [rcx+8]
0x180018a27  mov     rax, rdx
0x180018a2a  mov     rdx, [rcx]
0x180018a2d  mov     r9d, 3; unsigned int
0x180018a33  lea     rcx, [r11+8]
0x180018a37  mov     qword ptr [r11+18h], 0
0x180018a3f  mov     [r11-20h], rcx
0x180018a43  lea     rcx, [r11+18h]
0x180018a47  mov     [r11-28h], rcx
0x180018a4b  mov     rcx, rax; void *
0x180018a4e  mov     edx, [rdx]; unsigned int
0x180018a50  mov     [rsp+48h+arg_0], 0
0x180018a58  call    ?PinPropertyAllocate@@YAJPEAXKAEBU_GUID@@KPEAPEAXPEAK@Z; PinPropertyAllocate(void *,ulong,_GUID const &,ulong,void * *,ulong *)
0x180018a5d  mov     edi, eax
0x180018a5f  test    eax, eax
0x180018a61  jns     short loc_180018A92
0x180018a63  mov     r9d, eax; char *
0x180018a66  mov     edx, 156h; void *
0x180018a6b  mov     rcx, [rsp+48h]; this
0x180018a70  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180018a77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a7c  mov     rcx, [rsp+48h+Block]; Block
0x180018a81  test    rcx, rcx
0x180018a84  jz      short loc_180018AE0
0x180018a86  mov     edx, 8
0x180018a8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018a90  jmp     short loc_180018AE0
0x180018a92  mov     eax, [rsp+48h+arg_0]
0x180018a96  cmp     eax, 8
0x180018a99  jnb     short loc_180018AAA
0x180018a9b  mov     edi, 8007065Eh
0x180018aa0  mov     edx, 158h
0x180018aa5  mov     r9d, edi
0x180018aa8  jmp     short loc_180018A6B
0x180018aaa  mov     rbx, [rsp+48h+Block]
0x180018aaf  cmp     dword ptr [rbx+4], 0
0x180018ab3  jnz     short loc_180018AD8
0x180018ab5  mov     rcx, [rsp+48h]; this
0x180018aba  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180018ac1  mov     edi, 8007065Eh
0x180018ac6  mov     edx, 159h; void *
0x180018acb  mov     r9d, edi; char *
0x180018ace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ad3  mov     rcx, rbx
0x180018ad6  jmp     short loc_180018A86
0x180018ad8  mov     [r15], rbx
0x180018adb  xor     edi, edi
0x180018add  mov     [r14], eax
0x180018ae0  mov     rbx, [rsp+48h+arg_8]
0x180018ae5  mov     eax, edi
0x180018ae7  add     rsp, 30h
0x180018aeb  pop     r15
0x180018aed  pop     r14
0x180018aef  pop     rdi
0x180018af0  retn
```
