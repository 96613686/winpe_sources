# operator delete(void *)

- ea: `0x100426c30`
- end: `0x100426c5b`
- name: `??3@YAXPEAX@Z`
- size: `43`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100468a54`

## callees

- `0x100426c30`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100426c53`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( g_SOSHost )
  {
    if ( a1 )
      (*(void (__fastcall **)(_QWORD, void *))(*g_SOSMemObj + 128LL))(g_SOSMemObj, a1);
  }
  else
  {
    free(a1);
  }
}

```

## disassembly

```asm
0x100426c30  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100426c38  mov     rdx, rcx
0x100426c3b  jz      short loc_100426C53
0x100426c3d  test    rcx, rcx
0x100426c40  jz      short locret_100426C5A
0x100426c42  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100426c49  mov     rax, [rcx]
0x100426c4c  jmp     qword ptr [rax+80h]
0x100426c53  jmp     cs:__imp_free
0x100426c5a  retn
```
