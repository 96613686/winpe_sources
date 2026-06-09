# BfGetInstanceFromVolumeName

- ea: `0x14001e6fc`
- end: `0x14001e812`
- name: `BfGetInstanceFromVolumeName`
- size: `278`
- prototype: `__int64 __fastcall(PCUNICODE_STRING VolumeName)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001d2c0`
- `0x14001d974`
- `0x14001efcc`
- `0x14001f71c`

## callees

- `0x140001348`
- `0x14001e6fc`

## import_xrefs

- `FLTMGR!FltGetVolumeFromName` at `0x14001e729`
- `FLTMGR!FltGetVolumeFromName` at `0x14001e729`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14001e74f`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14001e74f`
- `FLTMGR!FltObjectDereference` at `0x14001e777`
- `FLTMGR!FltObjectDereference` at `0x14001e777`

## pseudocode

```c
__int64 __fastcall BfGetInstanceFromVolumeName(PCUNICODE_STRING VolumeName, PFLT_INSTANCE *a2)
{
  int v3; // edx
  NTSTATUS VolumeFromName; // ebx
  int v6; // r9d
  char v7; // [rsp+30h] [rbp-18h]
  NTSTATUS v8; // [rsp+38h] [rbp-10h]
  PFLT_VOLUME Volume; // [rsp+60h] [rbp+18h] BYREF
  PFLT_INSTANCE RetInstance; // [rsp+68h] [rbp+20h] BYREF

  Volume = 0;
  RetInstance = 0;
  VolumeFromName = FltGetVolumeFromName(g_BindFltState, VolumeName, &Volume);
  if ( VolumeFromName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_4;
    v8 = VolumeFromName;
    v6 = 44;
    v7 = -109;
    goto LABEL_9;
  }
  VolumeFromName = FltGetVolumeInstanceFromName(g_BindFltState, Volume, 0, &RetInstance);
  if ( VolumeFromName >= 0 )
  {
    *a2 = RetInstance;
    goto LABEL_4;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = VolumeFromName;
    v6 = 45;
    v7 = -102;
LABEL_9:
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      3,
      v6,
      (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
      v7,
      v8);
  }
LABEL_4:
  if ( Volume )
    FltObjectDereference(Volume);
  return (unsigned int)VolumeFromName;
}

```

## disassembly

```asm
0x14001e6fc  mov     rax, rsp
0x14001e6ff  mov     [rax+8], rbx
0x14001e703  push    rdi
0x14001e704  sub     rsp, 40h
0x14001e708  mov     rdi, rdx
0x14001e70b  mov     qword ptr [rax+18h], 0
0x14001e713  mov     rdx, rcx; VolumeName
0x14001e716  mov     qword ptr [rax+20h], 0
0x14001e71e  mov     rcx, cs:g_BindFltState; Filter
0x14001e725  lea     r8, [rax+18h]; RetVolume
0x14001e729  call    cs:__imp_FltGetVolumeFromName
0x14001e730  nop     dword ptr [rax+rax+00h]
0x14001e735  mov     ebx, eax
0x14001e737  test    eax, eax
0x14001e739  js      short loc_14001E791
0x14001e73b  mov     rdx, [rsp+48h+Volume]; Volume
0x14001e740  lea     r9, [rsp+48h+RetInstance]; RetInstance
0x14001e745  mov     rcx, cs:g_BindFltState; Filter
0x14001e74c  xor     r8d, r8d; InstanceName
0x14001e74f  call    cs:__imp_FltGetVolumeInstanceFromName
0x14001e756  nop     dword ptr [rax+rax+00h]
0x14001e75b  mov     ebx, eax
0x14001e75d  test    eax, eax
0x14001e75f  js      loc_14001E7FC
0x14001e765  mov     rax, [rsp+48h+RetInstance]
0x14001e76a  mov     [rdi], rax
0x14001e76d  mov     rcx, [rsp+48h+Volume]; FltObject
0x14001e772  test    rcx, rcx
0x14001e775  jz      short loc_14001E783
0x14001e777  call    cs:__imp_FltObjectDereference
0x14001e77e  nop     dword ptr [rax+rax+00h]
0x14001e783  mov     eax, ebx
0x14001e785  mov     rbx, [rsp+48h+arg_0]
0x14001e78a  add     rsp, 40h
0x14001e78e  pop     rdi
0x14001e78f  retn
0x14001e791  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e798  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e79f  jz      short loc_14001E76D
0x14001e7a1  mov     [rsp+48h+var_10], ebx
0x14001e7a5  mov     r9d, 2Ch ; ','
0x14001e7ab  mov     dword ptr [rsp+48h+var_18], 793h
0x14001e7b3  jmp     short loc_14001E7C7
0x14001e7b5  mov     [rsp+48h+var_10], ebx
0x14001e7b9  mov     r9d, 2Dh ; '-'
0x14001e7bf  mov     dword ptr [rsp+48h+var_18], 79Ah
0x14001e7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7ce  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001e7d5  mov     [rsp+48h+var_20], rax
0x14001e7da  mov     r8d, 3
0x14001e7e0  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14001e7e7  mov     dl, 2
0x14001e7e9  mov     [rsp+48h+var_28], rax
0x14001e7ee  mov     rcx, [rcx+40h]
0x14001e7f2  call    WPP_RECORDER_SF_sDd
0x14001e7f7  jmp     loc_14001E76D
0x14001e7fc  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e803  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e80a  jz      loc_14001E76D
0x14001e810  jmp     short loc_14001E7B5
```
