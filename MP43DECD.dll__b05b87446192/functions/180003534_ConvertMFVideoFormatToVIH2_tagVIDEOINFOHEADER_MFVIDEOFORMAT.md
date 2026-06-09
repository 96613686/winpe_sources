# ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)

- ea: `0x180003534`
- end: `0x180003584`
- name: `?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z`
- size: `80`
- prototype: `int(struct tagVIDEOINFOHEADER **, struct _MFVIDEOFORMAT *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e48`
- `0x180004560`
- `0x180004750`
- `0x180004ffc`
- `0x180007380`
- `0x180007800`

## callees

- `0x18000146c`
- `0x180003534`
- `0x18000358c`

## pseudocode

```c
__int64 __fastcall ConvertMFVideoFormatToVIH2(struct tagVIDEOINFOHEADER **a1, struct _MFVIDEOFORMAT *a2)
{
  struct tagVIDEOINFOHEADER *v4; // rax

  if ( !a1 || !a2 )
    return 2147500035LL;
  v4 = (struct tagVIDEOINFOHEADER *)operator new[](0x458u);
  *a1 = v4;
  if ( v4 )
    return ConvertMFVideoFormatToVIH3(v4, a2);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x180003534  mov     [rsp+arg_0], rbx
0x180003539  push    rdi
0x18000353a  sub     rsp, 20h
0x18000353e  mov     rbx, rdx
0x180003541  mov     rdi, rcx
0x180003544  test    rcx, rcx
0x180003547  jz      short loc_180003574
0x180003549  test    rdx, rdx
0x18000354c  jz      short loc_180003574
0x18000354e  mov     ecx, 458h; unsigned __int64
0x180003553  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003558  mov     [rdi], rax
0x18000355b  test    rax, rax
0x18000355e  jnz     short loc_180003567
0x180003560  mov     eax, 8007000Eh
0x180003565  jmp     short loc_180003579
0x180003567  mov     rdx, rbx; struct _MFVIDEOFORMAT *
0x18000356a  mov     rcx, rax; struct tagVIDEOINFOHEADER *
0x18000356d  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x180003572  jmp     short loc_180003579
0x180003574  mov     eax, 80004003h
0x180003579  mov     rbx, [rsp+28h+arg_0]
0x18000357e  add     rsp, 20h
0x180003582  pop     rdi
0x180003583  retn
```
