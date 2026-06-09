# VsmmMemXferIoctlConnectSrcOpen

- ea: `0x1400ab0e8`
- end: `0x1400ab322`
- name: `VsmmMemXferIoctlConnectSrcOpen`
- size: `570`
- prototype: `__int64 __fastcall(PVOID P, HANDLE Handle, KPROCESSOR_MODE AccessMode)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x14000f918`
- `0x14000fa14`
- `0x14002f724`
- `0x1400ab0e8`
- `0x1400ab3b4`
- `0x1400ab4e4`
- `0x1400f5094`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ab130`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ab130`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ab2e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ab2e8`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400ab1d3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400ab1d3`
- `ntoskrnl!IoFileObjectType` at `0x1400ab106`
- `ntoskrnl!IoFileObjectType` at `0x1400ab1b8`
- `ntoskrnl!ZwClose` at `0x1400ab2d4`
- `ntoskrnl!ZwClose` at `0x1400ab2d4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ab16b`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ab16b`

## string_xrefs

- `0x1400ab157`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400ab194`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400ab1f5`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400ab230`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400ab297`: `VsmmMemXferIoctlConnectSrcOpen`

## pseudocode

```c
__int64 __fastcall VsmmMemXferIoctlConnectSrcOpen(char *P, HANDLE Handle, KPROCESSOR_MODE AccessMode)
{
  _QWORD *v4; // rbx
  NTSTATUS v5; // eax
  PFILE_OBJECT v6; // rsi
  unsigned int v7; // edi
  __int64 v8; // rdx
  PDEVICE_OBJECT RelatedDeviceObject; // r14
  NTSTATUS v10; // eax
  __int64 v11; // rax
  HANDLE v12; // rax
  PFILE_OBJECT FileObject; // [rsp+40h] [rbp-28h] BYREF
  HANDLE v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = (HANDLE)-1LL;
  v4 = 0;
  FileObject = 0;
  v5 = ObReferenceObjectByHandle(Handle, 0x82u, (POBJECT_TYPE)IoFileObjectType, AccessMode, (PVOID *)&FileObject, 0);
  v6 = FileObject;
  v7 = v5;
  if ( v5 >= 0 )
  {
    RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
    if ( RelatedDeviceObject )
    {
      v10 = ObOpenObjectByPointer(v6, 0x200u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &v15);
      v7 = v10;
      if ( v10 >= 0 )
      {
        v11 = VsmmMemXferpConnectionAlloc(P);
        v4 = (_QWORD *)v11;
        if ( v11 )
        {
          *(_DWORD *)(v11 + 116) = 1;
          *(_DWORD *)(v11 + 112) = 2;
          v12 = v15;
          v4[17] = RelatedDeviceObject;
          v4[15] = v12;
          v4[16] = v6;
          VidAutoExpandPushLockAcquireExclusive(P + 8608);
          if ( *((_QWORD *)P + 1078) )
          {
            v7 = -1073741436;
            VidTraceErrorStatusInternal0(
              "VsmmMemXferIoctlConnectSrcOpen",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
              984,
              3221225860LL);
          }
          else
          {
            *((_QWORD *)P + 1078) = v4;
            v6 = 0;
            v4 = 0;
            v15 = (HANDLE)-1LL;
            v7 = 0;
          }
          VidAutoExpandPushLockReleaseExclusive(P + 8608);
        }
        else
        {
          v7 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmMemXferIoctlConnectSrcOpen",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
            965,
            3221225626LL);
        }
      }
      else
      {
        VidTraceErrorStatusInternal0(
          "VsmmMemXferIoctlConnectSrcOpen",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
          951,
          (unsigned int)v10);
      }
    }
    else
    {
      v7 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VsmmMemXferIoctlConnectSrcOpen",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
        928,
        3221225485LL);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemXferIoctlConnectSrcOpen",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
      916,
      (unsigned int)v5);
  }
  if ( v15 != (HANDLE)-1LL )
    ZwClose(v15);
  if ( v6 )
    ObfDereferenceObject(v6);
  if ( v4 )
  {
    LOBYTE(v8) = 1;
    VidOpCtrlBlock(v4 + 2, v8);
    VsmmMemXferpConnectionFreeInternal(v4);
  }
  return v7;
}

```

## disassembly

```asm
0x1400ab0e8  mov     r11, rsp
0x1400ab0eb  mov     [r11+8], rbx
0x1400ab0ef  mov     [r11+10h], rbp
0x1400ab0f3  push    rsi
0x1400ab0f4  push    rdi
0x1400ab0f5  push    r14
0x1400ab0f7  sub     rsp, 50h
0x1400ab0fb  mov     r9b, r8b; AccessMode
0x1400ab0fe  mov     qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x1400ab106  mov     r8, cs:__imp_IoFileObjectType
0x1400ab10d  mov     rbp, rcx
0x1400ab110  lea     rcx, [r11-28h]
0x1400ab114  mov     rax, rdx
0x1400ab117  xor     ebx, ebx
0x1400ab119  mov     edx, 82h; DesiredAccess
0x1400ab11e  mov     [r11-40h], rbx
0x1400ab122  mov     r8, [r8]; ObjectType
0x1400ab125  mov     [r11-48h], rcx
0x1400ab129  mov     rcx, rax; Handle
0x1400ab12c  mov     [r11-28h], rbx
0x1400ab130  call    cs:__imp_ObReferenceObjectByHandle
0x1400ab137  nop     dword ptr [rax+rax+00h]
0x1400ab13c  mov     rsi, [rsp+68h+FileObject]
0x1400ab141  mov     edi, eax
0x1400ab143  test    eax, eax
0x1400ab145  jns     short loc_1400AB168
0x1400ab147  mov     r9d, eax
0x1400ab14a  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400ab151  mov     r8d, 394h
0x1400ab157  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400ab15e  call    VidTraceErrorStatusInternal0
0x1400ab163  jmp     loc_1400AB2C6
0x1400ab168  mov     rcx, rsi; FileObject
0x1400ab16b  call    cs:__imp_IoGetRelatedDeviceObject
0x1400ab172  nop     dword ptr [rax+rax+00h]
0x1400ab177  mov     r14, rax
0x1400ab17a  test    rax, rax
0x1400ab17d  jnz     short loc_1400AB1A5
0x1400ab17f  mov     edi, 0C000000Dh
0x1400ab184  mov     r9d, edi
0x1400ab187  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400ab18e  mov     r8d, 3A0h
0x1400ab194  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400ab19b  call    VidTraceErrorStatusInternal0
0x1400ab1a0  jmp     loc_1400AB2C6
0x1400ab1a5  lea     rax, [rsp+68h+arg_18]
0x1400ab1ad  xor     r9d, r9d; DesiredAccess
0x1400ab1b0  mov     [rsp+68h+Handle], rax; Handle
0x1400ab1b5  xor     r8d, r8d; PassedAccessState
0x1400ab1b8  mov     rax, cs:__imp_IoFileObjectType
0x1400ab1bf  mov     edx, 200h; HandleAttributes
0x1400ab1c4  mov     [rsp+68h+AccessMode], bl; AccessMode
0x1400ab1c8  mov     rcx, [rax]
0x1400ab1cb  mov     [rsp+68h+ObjectType], rcx; ObjectType
0x1400ab1d0  mov     rcx, rsi; Object
0x1400ab1d3  call    cs:__imp_ObOpenObjectByPointer
0x1400ab1da  nop     dword ptr [rax+rax+00h]
0x1400ab1df  mov     edi, eax
0x1400ab1e1  test    eax, eax
0x1400ab1e3  jns     short loc_1400AB206
0x1400ab1e5  mov     r9d, eax
0x1400ab1e8  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400ab1ef  mov     r8d, 3B7h
0x1400ab1f5  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400ab1fc  call    VidTraceErrorStatusInternal0
0x1400ab201  jmp     loc_1400AB2C6
0x1400ab206  mov     edx, 1
0x1400ab20b  mov     rcx, rbp; P
0x1400ab20e  call    VsmmMemXferpConnectionAlloc
0x1400ab213  mov     rbx, rax
0x1400ab216  test    rax, rax
0x1400ab219  jnz     short loc_1400AB241
0x1400ab21b  mov     edi, 0C000009Ah
0x1400ab220  mov     r9d, edi
0x1400ab223  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400ab22a  mov     r8d, 3C5h
0x1400ab230  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400ab237  call    VidTraceErrorStatusInternal0
0x1400ab23c  jmp     loc_1400AB2C6
0x1400ab241  mov     dword ptr [rax+74h], 1
0x1400ab248  mov     dword ptr [rax+70h], 2
0x1400ab24f  mov     rax, [rsp+68h+arg_18]
0x1400ab257  mov     [rbx+88h], r14
0x1400ab25e  lea     r14, [rbp+21A0h]
0x1400ab265  mov     rcx, r14
0x1400ab268  mov     [rbx+78h], rax
0x1400ab26c  mov     [rbx+80h], rsi
0x1400ab273  call    VidAutoExpandPushLockAcquireExclusive
0x1400ab278  cmp     qword ptr [rbp+21B0h], 0
0x1400ab280  jz      short loc_1400AB2A5
0x1400ab282  mov     edi, 0C0000184h
0x1400ab287  mov     r9d, edi
0x1400ab28a  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400ab291  mov     r8d, 3D8h
0x1400ab297  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400ab29e  call    VidTraceErrorStatusInternal0
0x1400ab2a3  jmp     short loc_1400AB2BE
0x1400ab2a5  mov     [rbp+21B0h], rbx
0x1400ab2ac  xor     esi, esi
0x1400ab2ae  xor     ebx, ebx
0x1400ab2b0  mov     [rsp+68h+arg_18], 0FFFFFFFFFFFFFFFFh
0x1400ab2bc  xor     edi, edi
0x1400ab2be  mov     rcx, r14
0x1400ab2c1  call    VidAutoExpandPushLockReleaseExclusive
0x1400ab2c6  mov     rcx, [rsp+68h+arg_18]; Handle
0x1400ab2ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400ab2d2  jz      short loc_1400AB2E0
0x1400ab2d4  call    cs:__imp_ZwClose
0x1400ab2db  nop     dword ptr [rax+rax+00h]
0x1400ab2e0  test    rsi, rsi
0x1400ab2e3  jz      short loc_1400AB2F4
0x1400ab2e5  mov     rcx, rsi; Object
0x1400ab2e8  call    cs:__imp_ObfDereferenceObject
0x1400ab2ef  nop     dword ptr [rax+rax+00h]
0x1400ab2f4  test    rbx, rbx
0x1400ab2f7  jz      short loc_1400AB30C
0x1400ab2f9  lea     rcx, [rbx+10h]
0x1400ab2fd  mov     dl, 1
0x1400ab2ff  call    VidOpCtrlBlock
0x1400ab304  mov     rcx, rbx; P
0x1400ab307  call    VsmmMemXferpConnectionFreeInternal
0x1400ab30c  mov     rbx, [rsp+68h+arg_0]
0x1400ab311  mov     eax, edi
0x1400ab313  mov     rbp, [rsp+68h+arg_8]
0x1400ab318  add     rsp, 50h
0x1400ab31c  pop     r14
0x1400ab31e  pop     rdi
0x1400ab31f  pop     rsi
0x1400ab320  retn
```
