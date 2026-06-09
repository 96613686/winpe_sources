# ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)

- ea: `0x1800035f4`
- end: `0x180003644`
- name: `?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(struct tagVIDEOINFOHEADER **, struct _MFVIDEOFORMAT *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f08`
- `0x180004620`
- `0x180004810`
- `0x1800050bc`
- `0x180007440`
- `0x1800078c0`

## callees

- `0x18000149c`
- `0x1800035f4`
- `0x18000364c`

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
0x1800035f4  mov     [rsp+arg_0], rbx
0x1800035f9  push    rdi
0x1800035fa  sub     rsp, 20h
0x1800035fe  mov     rbx, rdx
0x180003601  mov     rdi, rcx
0x180003604  test    rcx, rcx
0x180003607  jz      short loc_180003634
0x180003609  test    rdx, rdx
0x18000360c  jz      short loc_180003634
0x18000360e  mov     ecx, 458h; unsigned __int64
0x180003613  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003618  mov     [rdi], rax
0x18000361b  test    rax, rax
0x18000361e  jnz     short loc_180003627
0x180003620  mov     eax, 8007000Eh
0x180003625  jmp     short loc_180003639
0x180003627  mov     rdx, rbx; struct _MFVIDEOFORMAT *
0x18000362a  mov     rcx, rax; struct tagVIDEOINFOHEADER *
0x18000362d  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x180003632  jmp     short loc_180003639
0x180003634  mov     eax, 80004003h
0x180003639  mov     rbx, [rsp+28h+arg_0]
0x18000363e  add     rsp, 20h
0x180003642  pop     rdi
0x180003643  retn
```
