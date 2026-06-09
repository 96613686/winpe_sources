# AipkUnloadRegCache

- ea: `0x14002920c`
- end: `0x1400292bf`
- name: `AipkUnloadRegCache`
- size: `179`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400252dc`

## callees

- `0x14002920c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400292ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400292ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140029250`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140029250`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140029265`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140029265`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400292a1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400292a1`
- `ntoskrnl!ZwUnloadKeyEx` at `0x140029281`
- `ntoskrnl!ZwUnloadKeyEx` at `0x140029281`

## pseudocode

```c
void AipkUnloadRegCache()
{
  struct _OBJECT_ATTRIBUTES TargetKey; // [rsp+20h] [rbp-38h] BYREF

  *(&TargetKey.Length + 1) = 0;
  *(&TargetKey.Attributes + 1) = 0;
  if ( AipAppxRegCacheInitialized )
  {
    TargetKey.RootDirectory = 0;
    TargetKey.Length = 48;
    TargetKey.ObjectName = (PUNICODE_STRING)L"NP";
    TargetKey.Attributes = 576;
    *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&AipAppxRegCache, 0);
    if ( (_BYTE)qword_140019430 )
    {
      if ( ZwUnloadKeyEx(&TargetKey, 0) >= 0 )
        LOBYTE(qword_140019430) = 0;
    }
    ExReleasePushLockExclusiveEx(&AipAppxRegCache, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x14002920c  sub     rsp, 58h
0x140029210  xor     eax, eax
0x140029212  cmp     cs:AipAppxRegCacheInitialized, al
0x140029218  mov     dword ptr [rsp+58h+TargetKey+4], eax
0x14002921c  mov     dword ptr [rsp+58h+TargetKey+1Ch], eax
0x140029220  jz      loc_1400292B9
0x140029226  mov     [rsp+58h+TargetKey.RootDirectory], rax
0x14002922b  xorps   xmm0, xmm0
0x14002922e  lea     rax, aNp; "NP"
0x140029235  mov     [rsp+58h+TargetKey.Length], 30h ; '0'
0x14002923d  mov     [rsp+58h+TargetKey.ObjectName], rax
0x140029242  mov     [rsp+58h+TargetKey.Attributes], 240h
0x14002924a  movdqu  xmmword ptr [rsp+58h+TargetKey.SecurityDescriptor], xmm0
0x140029250  call    cs:__imp_KeEnterCriticalRegion
0x140029257  nop     dword ptr [rax+rax+00h]
0x14002925c  xor     edx, edx
0x14002925e  lea     rcx, AipAppxRegCache
0x140029265  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002926c  nop     dword ptr [rax+rax+00h]
0x140029271  cmp     byte ptr cs:qword_140019430, 0
0x140029278  jz      short loc_140029298
0x14002927a  xor     edx, edx; Event
0x14002927c  lea     rcx, [rsp+58h+TargetKey]; TargetKey
0x140029281  call    cs:__imp_ZwUnloadKeyEx
0x140029288  nop     dword ptr [rax+rax+00h]
0x14002928d  test    eax, eax
0x14002928f  js      short loc_140029298
0x140029291  mov     byte ptr cs:qword_140019430, 0
0x140029298  xor     edx, edx
0x14002929a  lea     rcx, AipAppxRegCache
0x1400292a1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400292a8  nop     dword ptr [rax+rax+00h]
0x1400292ad  call    cs:__imp_KeLeaveCriticalRegion
0x1400292b4  nop     dword ptr [rax+rax+00h]
0x1400292b9  add     rsp, 58h
0x1400292bd  retn
```
