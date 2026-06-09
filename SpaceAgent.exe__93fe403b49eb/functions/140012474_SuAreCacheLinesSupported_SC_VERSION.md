# SuAreCacheLinesSupported(_SC_VERSION)

- ea: `0x140012474`
- end: `0x1400124b4`
- name: `?SuAreCacheLinesSupported@@YAHW4_SC_VERSION@@@Z`
- size: `64`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400105bc`
- `0x140011fb4`

## callees

- `0x1400084ac`
- `0x140012474`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400124a6`
- `KERNEL32!LocalFree` at `0x1400124a6`

## pseudocode

```c
__int64 __fastcall SuAreCacheLinesSupported(unsigned int a1)
{
  unsigned int v1; // ebx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  hMem = 0;
  if ( a1 >= 0x1B )
  {
    if ( (unsigned int)SuGetControl((struct _SP_CONTROL_INFO **)&hMem) )
      v1 = *((unsigned __int8 *)hMem + 49);
    if ( hMem )
      LocalFree(hMem);
  }
  return v1;
}

```

## disassembly

```asm
0x140012474  push    rbx
0x140012476  sub     rsp, 20h
0x14001247a  xor     ebx, ebx
0x14001247c  mov     [rsp+28h+hMem], 0
0x140012485  cmp     ecx, 1Bh
0x140012488  jb      short loc_1400124AC
0x14001248a  lea     rcx, [rsp+28h+hMem]; struct _SP_CONTROL_INFO **
0x14001248f  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x140012494  mov     rcx, [rsp+28h+hMem]; hMem
0x140012499  test    eax, eax
0x14001249b  jz      short loc_1400124A1
0x14001249d  movzx   ebx, byte ptr [rcx+31h]
0x1400124a1  test    rcx, rcx
0x1400124a4  jz      short loc_1400124AC
0x1400124a6  call    cs:__imp_LocalFree
0x1400124ac  mov     eax, ebx
0x1400124ae  add     rsp, 20h
0x1400124b2  pop     rbx
0x1400124b3  retn
```
