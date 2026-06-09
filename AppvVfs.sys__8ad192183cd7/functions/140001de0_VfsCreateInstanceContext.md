# VfsCreateInstanceContext

- ea: `0x140001de0`
- end: `0x140001fad`
- name: `VfsCreateInstanceContext`
- size: `461`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, int, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024250`

## callees

- `0x140001de0`
- `0x14001171c`
- `0x1400117ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001f6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014564`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014564`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140001e52`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140001e52`
- `FLTMGR!FltObjectDereference` at `0x140001e7a`
- `FLTMGR!FltObjectDereference` at `0x140001e7a`
- `FLTMGR!FltSetInstanceContext` at `0x140001f3b`
- `FLTMGR!FltSetInstanceContext` at `0x140001f3b`
- `FLTMGR!FltAllocateContext` at `0x140001eb5`
- `FLTMGR!FltAllocateContext` at `0x140001eb5`
- `FLTMGR!FltReleaseContext` at `0x140001f8e`
- `FLTMGR!FltReleaseContext` at `0x140014584`
- `FLTMGR!FltReleaseContext` at `0x140001f8e`
- `FLTMGR!FltReleaseContext` at `0x140014584`

## pseudocode

```c
__int64 __fastcall VfsCreateInstanceContext(PFLT_INSTANCE Instance, int a2, PFLT_CONTEXT *a3)
{
  __int64 result; // rax
  NTSTATUS VolumeFromInstance; // ebx
  _OWORD *v7; // rax
  PFLT_VOLUME RetVolume; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+40h] [rbp-28h] BYREF
  PVOID P[4]; // [rsp+48h] [rbp-20h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+88h] [rbp+20h] BYREF

  NewContext = 0;
  v9 = 0;
  P[0] = 0;
  P[1] = 0;
  if ( a2 == 20 || (result = VfsGetVpbFromInstance(Instance, &v9), (int)result >= 0) )
  {
    RetVolume = 0;
    P[1] = 0;
    LODWORD(P[0]) = 0;
    VolumeFromInstance = FltGetVolumeFromInstance(Instance, &RetVolume);
    if ( VolumeFromInstance >= 0 )
    {
      VolumeFromInstance = VfsGetVolumeName(RetVolume, (PUNICODE_STRING)P);
      FltObjectDereference(RetVolume);
    }
    if ( VolumeFromInstance >= 0 )
    {
      VolumeFromInstance = FltAllocateContext(VfsData, 2u, 0x28u, (POOL_TYPE)512, &NewContext);
      if ( VolumeFromInstance >= 0 )
      {
        v7 = NewContext;
        *(_OWORD *)NewContext = 0;
        v7[1] = 0;
        *((_QWORD *)v7 + 4) = 0;
        *(_QWORD *)NewContext = Instance;
        *((_DWORD *)NewContext + 6) = 0;
        *((_QWORD *)NewContext + 4) = v9;
        *(_OWORD *)((char *)NewContext + 8) = *(_OWORD *)P;
        P[1] = 0;
        VolumeFromInstance = FltSetInstanceContext(Instance, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, 0);
        if ( VolumeFromInstance >= 0 )
          *a3 = NewContext;
      }
    }
    if ( VolumeFromInstance < 0 )
    {
      if ( P[1] )
      {
        ExFreePoolWithTag(P[1], 0);
        P[1] = 0;
      }
      if ( NewContext )
        FltReleaseContext(NewContext);
    }
    return (unsigned int)VolumeFromInstance;
  }
  return result;
}

```

## disassembly

```asm
0x140001de0  mov     r11, rsp
0x140001de3  mov     [r11+8], rbx
0x140001de7  mov     [r11+10h], rsi
0x140001deb  push    rdi
0x140001dec  sub     rsp, 60h
0x140001df0  mov     rsi, r8
0x140001df3  mov     rdi, rcx
0x140001df6  mov     [rsp+68h+var_38], 0
0x140001dfe  mov     qword ptr [r11+20h], 0
0x140001e06  mov     qword ptr [r11-28h], 0
0x140001e0e  xor     eax, eax
0x140001e10  mov     [r11-20h], rax
0x140001e14  mov     [r11-18h], rax
0x140001e18  cmp     edx, 14h
0x140001e1b  jz      short loc_140001E32
0x140001e1d  lea     rdx, [r11-28h]
0x140001e21  call    VfsGetVpbFromInstance
0x140001e26  mov     [rsp+68h+var_38], eax
0x140001e2a  test    eax, eax
0x140001e2c  js      loc_140001F9C
0x140001e32  mov     [rsp+68h+RetVolume], 0
0x140001e3b  mov     [rsp+68h+P+8], 0
0x140001e44  xor     eax, eax
0x140001e46  mov     dword ptr [rsp+68h+P], eax
0x140001e4a  lea     rdx, [rsp+68h+RetVolume]; RetVolume
0x140001e4f  mov     rcx, rdi; Instance
0x140001e52  call    cs:__imp_FltGetVolumeFromInstance
0x140001e59  nop     dword ptr [rax+rax+00h]
0x140001e5e  mov     ebx, eax
0x140001e60  test    eax, eax
0x140001e62  js      short loc_140001E86
0x140001e64  lea     rdx, [rsp+68h+P]; VolumeName
0x140001e69  mov     rcx, [rsp+68h+RetVolume]; Volume
0x140001e6e  call    VfsGetVolumeName
0x140001e73  mov     ebx, eax
0x140001e75  mov     rcx, [rsp+68h+RetVolume]; FltObject
0x140001e7a  call    cs:__imp_FltObjectDereference
0x140001e81  nop     dword ptr [rax+rax+00h]
0x140001e86  mov     [rsp+68h+var_38], ebx
0x140001e8a  test    ebx, ebx
0x140001e8c  js      loc_140001F5C
0x140001e92  mov     edx, 2; ContextType
0x140001e97  lea     rax, [rsp+68h+NewContext]
0x140001e9f  mov     [rsp+68h+ReturnedContext], rax; ReturnedContext
0x140001ea4  mov     r9d, 200h; PoolType
0x140001eaa  lea     r8d, [rdx+26h]; ContextSize
0x140001eae  mov     rcx, cs:VfsData; Filter
0x140001eb5  call    cs:__imp_FltAllocateContext
0x140001ebc  nop     dword ptr [rax+rax+00h]
0x140001ec1  mov     ebx, eax
0x140001ec3  mov     [rsp+68h+var_38], eax
0x140001ec7  test    eax, eax
0x140001ec9  js      loc_140001F5C
0x140001ecf  xorps   xmm0, xmm0
0x140001ed2  xor     ecx, ecx
0x140001ed4  mov     rax, [rsp+68h+NewContext]
0x140001edc  movups  xmmword ptr [rax], xmm0
0x140001edf  movups  xmmword ptr [rax+10h], xmm0
0x140001ee3  mov     [rax+20h], rcx
0x140001ee7  mov     rax, [rsp+68h+NewContext]
0x140001eef  mov     [rax], rdi
0x140001ef2  mov     rax, [rsp+68h+NewContext]
0x140001efa  mov     [rax+18h], ecx
0x140001efd  mov     rcx, [rsp+68h+NewContext]
0x140001f05  mov     rax, [rsp+68h+var_28]
0x140001f0a  mov     [rcx+20h], rax
0x140001f0e  movups  xmm0, xmmword ptr [rsp+68h+P]
0x140001f13  mov     rax, [rsp+68h+NewContext]
0x140001f1b  movdqu  xmmword ptr [rax+8], xmm0
0x140001f20  mov     [rsp+68h+P+8], 0
0x140001f29  xor     r9d, r9d; OldContext
0x140001f2c  mov     r8, [rsp+68h+NewContext]; NewContext
0x140001f34  lea     edx, [r9+1]; Operation
0x140001f38  mov     rcx, rdi; Instance
0x140001f3b  call    cs:__imp_FltSetInstanceContext
0x140001f42  nop     dword ptr [rax+rax+00h]
0x140001f47  mov     ebx, eax
0x140001f49  mov     [rsp+68h+var_38], eax
0x140001f4d  test    eax, eax
0x140001f4f  js      short loc_140001F5C
0x140001f51  mov     rax, [rsp+68h+NewContext]
0x140001f59  mov     [rsi], rax
0x140001f5c  test    ebx, ebx
0x140001f5e  jns     short loc_140001F9A
0x140001f60  mov     rcx, [rsp+68h+P+8]; P
0x140001f65  test    rcx, rcx
0x140001f68  jz      short loc_140001F81
0x140001f6a  xor     edx, edx; Tag
0x140001f6c  call    cs:__imp_ExFreePoolWithTag
0x140001f73  nop     dword ptr [rax+rax+00h]
0x140001f78  mov     [rsp+68h+P+8], 0
0x140001f81  mov     rcx, [rsp+68h+NewContext]; Context
0x140001f89  test    rcx, rcx
0x140001f8c  jz      short loc_140001F9A
0x140001f8e  call    cs:__imp_FltReleaseContext
0x140001f95  nop     dword ptr [rax+rax+00h]
0x140001f9a  mov     eax, ebx
0x140001f9c  mov     rbx, [rsp+68h+arg_0]
0x140001fa1  mov     rsi, [rsp+68h+arg_8]
0x140001fa6  add     rsp, 60h
0x140001faa  pop     rdi
0x140001fab  retn
0x14001454a  push    rbp
0x14001454c  sub     rsp, 30h
0x140014550  mov     rbp, rdx
0x140014553  cmp     dword ptr [rbp+30h], 0
0x140014557  jge     short loc_140014591
0x140014559  mov     rcx, [rbp+50h]; P
0x14001455d  test    rcx, rcx
0x140014560  jz      short loc_140014578
0x140014562  xor     edx, edx; Tag
0x140014564  call    cs:__imp_ExFreePoolWithTag
0x14001456b  nop     dword ptr [rax+rax+00h]
0x140014570  mov     qword ptr [rbp+50h], 0
0x140014578  mov     rcx, [rbp+88h]; Context
0x14001457f  test    rcx, rcx
0x140014582  jz      short loc_140014591
0x140014584  call    cs:__imp_FltReleaseContext
0x14001458b  nop     dword ptr [rax+rax+00h]
0x140014590  nop
0x140014591  add     rsp, 30h
0x140014595  pop     rbp
0x140014596  retn
```
