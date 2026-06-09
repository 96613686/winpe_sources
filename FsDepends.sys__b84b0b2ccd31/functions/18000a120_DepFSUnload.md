# DepFSUnload

- ea: `0x18000a120`
- end: `0x18000a324`
- name: `DepFSUnload`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001430`
- `0x180001fb0`
- `0x18000a120`
- `0x18001127c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x18000a289`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000a289`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x18000a251`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x18000a251`
- `ntoskrnl!IoWMIRegistrationControl` at `0x18000a2d6`
- `ntoskrnl!IoWMIRegistrationControl` at `0x18000a2d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a1a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a209`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a27a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a2a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a1a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a209`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a27a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a2a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a19b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a1fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a26e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a29a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a19b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a1fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a26e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a29a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a17e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a235`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a17e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a235`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a166`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a224`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a166`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a224`
- `FLTMGR!FltUnregisterFilter` at `0x18000a218`
- `FLTMGR!FltUnregisterFilter` at `0x18000a218`

## pseudocode

```c
__int64 __fastcall DepFSUnload(char a1)
{
  struct _FLT_FILTER *v3; // rbx
  PDEVICE_OBJECT v4; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6e0896578ce0378c051a248e53d8716f_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( (a1 & 1) != 0 || !dword_180005180 )
  {
    if ( byte_180005195 )
    {
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
    }
    else
    {
      byte_180005195 = 1;
      DepFSNotifyChildren(0);
      if ( byte_180005197 )
      {
        v3 = (struct _FLT_FILTER *)Filter;
        Filter = 0;
        byte_180005197 = 0;
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        FltUnregisterFilter(v3);
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(&Resource, 1u);
      }
      if ( byte_1800051CC == 1 )
      {
        KeDeregisterBugCheckReasonCallback(&CallbackRecord);
        byte_1800051CC = 0;
      }
      byte_180005196 = 1;
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      ExDeleteResourceLite(&Resource);
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( WPPTraceSuite == 4 )
      {
        while ( v4 )
        {
          if ( v4->Vpb )
          {
            ((void (*)(void))pfnEtwUnregister)();
            v4->Vpb = 0;
          }
          v4 = v4->NextDevice;
        }
      }
      else if ( WPPTraceSuite == 2 )
      {
        IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
      }
      WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    }
    return 0;
  }
  else
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x18000a120  mov     [rsp+arg_0], rbx
0x18000a125  mov     [rsp+arg_8], rbp
0x18000a12a  push    rsi
0x18000a12b  sub     rsp, 20h
0x18000a12f  mov     ebx, ecx
0x18000a131  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a138  lea     rbp, WPP_GLOBAL_Control
0x18000a13f  cmp     rcx, rbp
0x18000a142  jz      short loc_18000A166
0x18000a144  mov     eax, [rcx+2Ch]
0x18000a147  test    al, 2
0x18000a149  jz      short loc_18000A166
0x18000a14b  cmp     byte ptr [rcx+29h], 4
0x18000a14f  jb      short loc_18000A166
0x18000a151  mov     rcx, [rcx+18h]
0x18000a155  lea     r8, WPP_6e0896578ce0378c051a248e53d8716f_Traceguids
0x18000a15c  mov     edx, 0Ch
0x18000a161  call    WPP_SF_
0x18000a166  call    cs:__imp_KeEnterCriticalRegion
0x18000a16d  nop     dword ptr [rax+rax+00h]
0x18000a172  lea     rsi, Resource
0x18000a179  mov     dl, 1; Wait
0x18000a17b  mov     rcx, rsi; Resource
0x18000a17e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000a185  nop     dword ptr [rax+rax+00h]
0x18000a18a  test    bl, 1
0x18000a18d  jnz     short loc_18000A1BD
0x18000a18f  cmp     cs:dword_180005180, 0
0x18000a196  jbe     short loc_18000A1BD
0x18000a198  mov     rcx, rsi; Resource
0x18000a19b  call    cs:__imp_ExReleaseResourceLite
0x18000a1a2  nop     dword ptr [rax+rax+00h]
0x18000a1a7  call    cs:__imp_KeLeaveCriticalRegion
0x18000a1ae  nop     dword ptr [rax+rax+00h]
0x18000a1b3  mov     eax, 0C0000001h
0x18000a1b8  jmp     loc_18000A2EB
0x18000a1bd  cmp     cs:byte_180005195, 0
0x18000a1c4  jnz     loc_18000A297
0x18000a1ca  xor     ecx, ecx
0x18000a1cc  mov     cs:byte_180005195, 1
0x18000a1d3  call    DepFSNotifyChildren
0x18000a1d8  cmp     cs:byte_180005197, 0
0x18000a1df  jz      short loc_18000A241
0x18000a1e1  mov     rbx, cs:Filter
0x18000a1e8  mov     rcx, rsi; Resource
0x18000a1eb  mov     cs:Filter, 0
0x18000a1f6  mov     cs:byte_180005197, 0
0x18000a1fd  call    cs:__imp_ExReleaseResourceLite
0x18000a204  nop     dword ptr [rax+rax+00h]
0x18000a209  call    cs:__imp_KeLeaveCriticalRegion
0x18000a210  nop     dword ptr [rax+rax+00h]
0x18000a215  mov     rcx, rbx; Filter
0x18000a218  call    cs:__imp_FltUnregisterFilter
0x18000a21f  nop     dword ptr [rax+rax+00h]
0x18000a224  call    cs:__imp_KeEnterCriticalRegion
0x18000a22b  nop     dword ptr [rax+rax+00h]
0x18000a230  mov     dl, 1; Wait
0x18000a232  mov     rcx, rsi; Resource
0x18000a235  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000a23c  nop     dword ptr [rax+rax+00h]
0x18000a241  cmp     cs:byte_1800051CC, 1
0x18000a248  jnz     short loc_18000A264
0x18000a24a  lea     rcx, CallbackRecord; CallbackRecord
0x18000a251  call    cs:__imp_KeDeregisterBugCheckReasonCallback
0x18000a258  nop     dword ptr [rax+rax+00h]
0x18000a25d  mov     cs:byte_1800051CC, 0
0x18000a264  mov     rcx, rsi; Resource
0x18000a267  mov     cs:byte_180005196, 1
0x18000a26e  call    cs:__imp_ExReleaseResourceLite
0x18000a275  nop     dword ptr [rax+rax+00h]
0x18000a27a  call    cs:__imp_KeLeaveCriticalRegion
0x18000a281  nop     dword ptr [rax+rax+00h]
0x18000a286  mov     rcx, rsi; Resource
0x18000a289  call    cs:__imp_ExDeleteResourceLite
0x18000a290  nop     dword ptr [rax+rax+00h]
0x18000a295  jmp     short loc_18000A2B2
0x18000a297  mov     rcx, rsi; Resource
0x18000a29a  call    cs:__imp_ExReleaseResourceLite
0x18000a2a1  nop     dword ptr [rax+rax+00h]
0x18000a2a6  call    cs:__imp_KeLeaveCriticalRegion
0x18000a2ad  nop     dword ptr [rax+rax+00h]
0x18000a2b2  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a2b9  cmp     rbx, rbp
0x18000a2bc  jz      short loc_18000A2E9
0x18000a2be  mov     eax, cs:WPPTraceSuite
0x18000a2c4  cmp     eax, 4
0x18000a2c7  jz      short loc_18000A31D
0x18000a2c9  cmp     eax, 2
0x18000a2cc  jnz     short loc_18000A2E2
0x18000a2ce  mov     edx, 80000002h; Action
0x18000a2d3  mov     rcx, rbx; DeviceObject
0x18000a2d6  call    cs:__imp_IoWMIRegistrationControl
0x18000a2dd  nop     dword ptr [rax+rax+00h]
0x18000a2e2  mov     cs:WPP_GLOBAL_Control, rbp
0x18000a2e9  xor     eax, eax
0x18000a2eb  mov     rbx, [rsp+28h+arg_0]
0x18000a2f0  mov     rbp, [rsp+28h+arg_8]
0x18000a2f5  add     rsp, 20h
0x18000a2f9  pop     rsi
0x18000a2fa  retn
0x18000a2fc  mov     rcx, [rbx+38h]
0x18000a300  test    rcx, rcx
0x18000a303  jz      short loc_18000A319
0x18000a305  mov     rax, cs:pfnEtwUnregister
0x18000a30c  call    _guard_dispatch_icall
0x18000a311  mov     qword ptr [rbx+38h], 0
0x18000a319  mov     rbx, [rbx+10h]
0x18000a31d  test    rbx, rbx
0x18000a320  jnz     short loc_18000A2FC
0x18000a322  jmp     short loc_18000A2E2
```
