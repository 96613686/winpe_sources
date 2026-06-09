# CCiFileMapEnumContext::MoveToNextFileMapFile(void)

- ea: `0x180002748`
- end: `0x1800028e4`
- name: `?MoveToNextFileMapFile@CCiFileMapEnumContext@@QEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(CCiFileMapEnumContext *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000b874`
- `0x180074d00`

## callees

- `0x180002748`
- `0x1800028f0`
- `0x1800038e0`
- `0x180004500`
- `0x18000b694`
- `0x18001f634`
- `0x1800293a0`
- `0x180098b08`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x1800027e9`
- `ntdll!NtQueryDirectoryFile` at `0x1800027e9`

## pseudocode

```c
__int64 __fastcall CCiFileMapEnumContext::MoveToNextFileMapFile(CCiFileMapEnumContext *this)
{
  bool v2; // zf
  NTSTATUS DirectoryFile; // eax
  NTSTATUS MapTargetDirectory; // ecx
  void *v5; // rdx
  unsigned __int64 v6; // rdx
  unsigned __int64 v8; // [rsp+60h] [rbp-48h] BYREF
  struct _UNICODE_STRING v9; // [rsp+68h] [rbp-40h] BYREF

  v8 = 0;
  v9 = 0;
  CFilemapEnumerationLookupContext::Close(this);
  v2 = *((_BYTE *)this + 49) == 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( !v2 )
  {
    LuaCdfFreeContext((char *)this + 72);
    *((_BYTE *)this + 49) = 0;
  }
  while ( 1 )
  {
    DirectoryFile = NtQueryDirectoryFile(
                      *((HANDLE *)this + 5),
                      0,
                      0,
                      0,
                      (PIO_STATUS_BLOCK)((char *)this + 56),
                      (char *)this + 208,
                      0x210u,
                      FileDirectoryInformation,
                      1u,
                      0,
                      *((_BYTE *)this + 48));
    *((_BYTE *)this + 48) = 0;
    MapTargetDirectory = DirectoryFile;
    if ( DirectoryFile < 0 )
      break;
    if ( (*((_BYTE *)this + 264) & 0x10) == 0 )
    {
      v5 = (void *)*((_QWORD *)this + 5);
      v9.Length = *((_WORD *)this + 134);
      v9.MaximumLength = v9.Length;
      v9.Buffer = (PWSTR)((char *)this + 272);
      MapTargetDirectory = CFilemapEnumerationLookupContext::OpenRelativeFile(this, v5, &v9);
      if ( MapTargetDirectory >= 0 )
      {
        *((_QWORD *)this + 9) = 0;
        *((_QWORD *)this + 10) = 0;
        MapTargetDirectory = CdfInitializeContext(this, (char *)this + 72);
        if ( MapTargetDirectory >= 0 )
        {
          *((_BYTE *)this + 49) = 1;
          MapTargetDirectory = LuaCdfGetMapTargetDirectory((char *)this + 72, (char *)this + 88, 0, &v8);
          if ( MapTargetDirectory >= 0 )
          {
            v6 = v8;
            *((_QWORD *)this + 12) = 0;
            if ( v6 <= *((_QWORD *)this + 13)
              || (MapTargetDirectory = RtlReallocateLUnicodeString(0, v6, (char *)this + 96), MapTargetDirectory >= 0) )
            {
              MapTargetDirectory = LuaCdfGetMapTargetDirectory(
                                     (char *)this + 72,
                                     (char *)this + 88,
                                     (char *)this + 96,
                                     &v8);
              if ( MapTargetDirectory >= 0 )
                return 0;
            }
          }
        }
      }
      return (unsigned int)MapTargetDirectory;
    }
  }
  return (unsigned int)MapTargetDirectory;
}

```

## disassembly

```asm
0x180002748  push    rbx
0x18000274a  push    rsi
0x18000274b  push    rdi
0x18000274c  push    r14
0x18000274e  sub     rsp, 88h
0x180002755  mov     rax, cs:__security_cookie
0x18000275c  xor     rax, rsp
0x18000275f  mov     [rsp+0A8h+var_30], rax
0x180002764  xorps   xmm0, xmm0
0x180002767  mov     [rsp+0A8h+var_48], 0
0x180002770  movups  xmmword ptr [rsp+0A8h+var_40.Length], xmm0
0x180002775  mov     rbx, rcx
0x180002778  call    ?Close@CFilemapEnumerationLookupContext@@QEAAXXZ; CFilemapEnumerationLookupContext::Close(void)
0x18000277d  cmp     byte ptr [rbx+31h], 0
0x180002781  lea     r14, [rbx+58h]
0x180002785  mov     dword ptr [r14], 0
0x18000278c  mov     qword ptr [rbx+20h], 0
0x180002794  jz      short loc_1800027A3
0x180002796  lea     rcx, [rbx+48h]
0x18000279a  call    LuaCdfFreeContext
0x18000279f  mov     byte ptr [rbx+31h], 0
0x1800027a3  lea     rdi, [rbx+0D0h]
0x1800027aa  lea     rsi, [rbx+38h]
0x1800027ae  mov     al, [rbx+30h]
0x1800027b1  xor     r9d, r9d; ApcContext
0x1800027b4  mov     rcx, [rbx+28h]; FileHandle
0x1800027b8  xor     r8d, r8d; ApcRoutine
0x1800027bb  mov     [rsp+0A8h+RestartScan], al; RestartScan
0x1800027bf  xor     edx, edx; Event
0x1800027c1  mov     [rsp+0A8h+FileName], 0; FileName
0x1800027ca  mov     [rsp+0A8h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1800027cf  mov     [rsp+0A8h+FileInformationClass], 1; FileInformationClass
0x1800027d7  mov     [rsp+0A8h+Length], 210h; Length
0x1800027df  mov     [rsp+0A8h+FileInformation], rdi; FileInformation
0x1800027e4  mov     [rsp+0A8h+IoStatusBlock], rsi; IoStatusBlock
0x1800027e9  call    cs:__imp_NtQueryDirectoryFile
0x1800027f0  nop     dword ptr [rax+rax+00h]
0x1800027f5  mov     byte ptr [rbx+30h], 0
0x1800027f9  mov     ecx, eax
0x1800027fb  test    eax, eax
0x1800027fd  js      loc_1800028C7
0x180002803  test    byte ptr [rbx+108h], 10h
0x18000280a  jnz     short loc_1800027AE
0x18000280c  movzx   eax, word ptr [rbx+10Ch]
0x180002813  lea     r8, [rsp+0A8h+var_40]; struct _UNICODE_STRING *
0x180002818  mov     rdx, [rbx+28h]; void *
0x18000281c  mov     rcx, rbx; this
0x18000281f  mov     [rsp+0A8h+var_40.Length], ax
0x180002824  mov     [rsp+0A8h+var_40.MaximumLength], ax
0x180002829  lea     rax, [rbx+110h]
0x180002830  mov     [rsp+0A8h+var_40.Buffer], rax
0x180002835  call    ?OpenRelativeFile@CFilemapEnumerationLookupContext@@QEAAJPEAXPEAU_UNICODE_STRING@@@Z; CFilemapEnumerationLookupContext::OpenRelativeFile(void *,_UNICODE_STRING *)
0x18000283a  mov     ecx, eax
0x18000283c  test    eax, eax
0x18000283e  js      loc_1800028C7
0x180002844  lea     rdi, [rbx+48h]
0x180002848  mov     rcx, rbx
0x18000284b  mov     rdx, rdi
0x18000284e  mov     qword ptr [rdi], 0
0x180002855  mov     qword ptr [rdi+8], 0
0x18000285d  call    CdfInitializeContext
0x180002862  mov     ecx, eax
0x180002864  test    eax, eax
0x180002866  js      short loc_1800028C7
0x180002868  lea     r9, [rsp+0A8h+var_48]
0x18000286d  mov     byte ptr [rbx+31h], 1
0x180002871  xor     r8d, r8d
0x180002874  mov     rdx, r14
0x180002877  mov     rcx, rdi
0x18000287a  call    LuaCdfGetMapTargetDirectory
0x18000287f  mov     ecx, eax
0x180002881  test    eax, eax
0x180002883  js      short loc_1800028C7
0x180002885  mov     rdx, [rsp+0A8h+var_48]
0x18000288a  lea     rsi, [rbx+60h]
0x18000288e  mov     qword ptr [rsi], 0
0x180002895  cmp     rdx, [rbx+68h]
0x180002899  jbe     short loc_1800028AB
0x18000289b  mov     r8, rsi
0x18000289e  xor     ecx, ecx
0x1800028a0  call    RtlReallocateLUnicodeString
0x1800028a5  mov     ecx, eax
0x1800028a7  test    eax, eax
0x1800028a9  js      short loc_1800028C7
0x1800028ab  lea     r9, [rsp+0A8h+var_48]
0x1800028b0  mov     r8, rsi
0x1800028b3  mov     rdx, r14
0x1800028b6  mov     rcx, rdi
0x1800028b9  call    LuaCdfGetMapTargetDirectory
0x1800028be  mov     ecx, eax
0x1800028c0  xor     eax, eax
0x1800028c2  test    ecx, ecx
0x1800028c4  cmovns  ecx, eax
0x1800028c7  mov     eax, ecx
0x1800028c9  mov     rcx, [rsp+0A8h+var_30]
0x1800028ce  xor     rcx, rsp; StackCookie
0x1800028d1  call    __security_check_cookie
0x1800028d6  add     rsp, 88h
0x1800028dd  pop     r14
0x1800028df  pop     rdi
0x1800028e0  pop     rsi
0x1800028e1  pop     rbx
0x1800028e2  retn
```
