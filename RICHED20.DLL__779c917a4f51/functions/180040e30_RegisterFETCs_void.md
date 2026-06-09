# RegisterFETCs(void)

- ea: `0x180040e30`
- end: `0x180040f29`
- name: `?RegisterFETCs@@YAXXZ`
- size: `249`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180031ba0`

## import_xrefs

- `USER32!RegisterClipboardFormatA` at `0x180040e3b`
- `USER32!RegisterClipboardFormatA` at `0x180040e4f`
- `USER32!RegisterClipboardFormatA` at `0x180040e63`
- `USER32!RegisterClipboardFormatA` at `0x180040e77`
- `USER32!RegisterClipboardFormatA` at `0x180040e8b`
- `USER32!RegisterClipboardFormatA` at `0x180040e9f`
- `USER32!RegisterClipboardFormatA` at `0x180040eb3`
- `USER32!RegisterClipboardFormatA` at `0x180040ec7`
- `USER32!RegisterClipboardFormatA` at `0x180040edb`
- `USER32!RegisterClipboardFormatA` at `0x180040eef`
- `USER32!RegisterClipboardFormatA` at `0x180040f03`
- `USER32!RegisterClipboardFormatA` at `0x180040f17`
- `USER32!RegisterClipboardFormatA` at `0x180040e3b`
- `USER32!RegisterClipboardFormatA` at `0x180040e4f`
- `USER32!RegisterClipboardFormatA` at `0x180040e63`
- `USER32!RegisterClipboardFormatA` at `0x180040e77`
- `USER32!RegisterClipboardFormatA` at `0x180040e8b`
- `USER32!RegisterClipboardFormatA` at `0x180040e9f`
- `USER32!RegisterClipboardFormatA` at `0x180040eb3`
- `USER32!RegisterClipboardFormatA` at `0x180040ec7`
- `USER32!RegisterClipboardFormatA` at `0x180040edb`
- `USER32!RegisterClipboardFormatA` at `0x180040eef`
- `USER32!RegisterClipboardFormatA` at `0x180040f03`
- `USER32!RegisterClipboardFormatA` at `0x180040f17`

## string_xrefs

- `0x180040ecd`: `Link Source`
- `0x180040e91`: `Object Descriptor`

## pseudocode

```c
void RegisterFETCs(void)
{
  LOWORD(xmmword_1800A30F0) = RegisterClipboardFormatA("Rich Text Format");
  LOWORD(g_rgFETC) = RegisterClipboardFormatA("RTF in UTF8");
  LOWORD(xmmword_1800A3110) = RegisterClipboardFormatA("RTF with NCRs for nonASCII");
  LOWORD(xmmword_1800A3290) = RegisterClipboardFormatA("RTF As Text");
  word_1800A32D0 = RegisterClipboardFormatA("RICHEDIT");
  LOWORD(xmmword_1800A3170) = RegisterClipboardFormatA("Object Descriptor");
  LOWORD(xmmword_1800A3130) = RegisterClipboardFormatA("Embedded Object");
  word_1800A3150 = RegisterClipboardFormatA("Embed Source");
  word_1800A3190 = RegisterClipboardFormatA("Link Source");
  LOWORD(xmmword_1800A3210) = RegisterClipboardFormatA("Rich Text Format Without Objects");
  word_1800A32B0 = RegisterClipboardFormatA("RichEdit Text and Objects");
  word_1800A3270 = RegisterClipboardFormatA("FileName");
}

```

## disassembly

```asm
0x180040e30  sub     rsp, 28h
0x180040e34  lea     rcx, szFormat; "Rich Text Format"
0x180040e3b  call    cs:__imp_RegisterClipboardFormatA
0x180040e41  lea     rcx, aRtfInUtf8; "RTF in UTF8"
0x180040e48  mov     word ptr cs:xmmword_1800A30F0, ax
0x180040e4f  call    cs:__imp_RegisterClipboardFormatA
0x180040e55  lea     rcx, aRtfWithNcrsFor; "RTF with NCRs for nonASCII"
0x180040e5c  mov     word ptr cs:?g_rgFETC@@3PAUtagFORMATETC@@A, ax; tagFORMATETC near * g_rgFETC
0x180040e63  call    cs:__imp_RegisterClipboardFormatA
0x180040e69  lea     rcx, aRtfAsText; "RTF As Text"
0x180040e70  mov     word ptr cs:xmmword_1800A3110, ax
0x180040e77  call    cs:__imp_RegisterClipboardFormatA
0x180040e7d  lea     rcx, aRichedit; "RICHEDIT"
0x180040e84  mov     word ptr cs:xmmword_1800A3290, ax
0x180040e8b  call    cs:__imp_RegisterClipboardFormatA
0x180040e91  lea     rcx, aObjectDescript; "Object Descriptor"
0x180040e98  mov     cs:word_1800A32D0, ax
0x180040e9f  call    cs:__imp_RegisterClipboardFormatA
0x180040ea5  lea     rcx, aEmbeddedObject; "Embedded Object"
0x180040eac  mov     word ptr cs:xmmword_1800A3170, ax
0x180040eb3  call    cs:__imp_RegisterClipboardFormatA
0x180040eb9  lea     rcx, aEmbedSource; "Embed Source"
0x180040ec0  mov     word ptr cs:xmmword_1800A3130, ax
0x180040ec7  call    cs:__imp_RegisterClipboardFormatA
0x180040ecd  lea     rcx, aLinkSource; "Link Source"
0x180040ed4  mov     cs:word_1800A3150, ax
0x180040edb  call    cs:__imp_RegisterClipboardFormatA
0x180040ee1  lea     rcx, aRichTextFormat_0; "Rich Text Format Without Objects"
0x180040ee8  mov     cs:word_1800A3190, ax
0x180040eef  call    cs:__imp_RegisterClipboardFormatA
0x180040ef5  lea     rcx, aRicheditTextAn; "RichEdit Text and Objects"
0x180040efc  mov     word ptr cs:xmmword_1800A3210, ax
0x180040f03  call    cs:__imp_RegisterClipboardFormatA
0x180040f09  lea     rcx, aFilename; "FileName"
0x180040f10  mov     cs:word_1800A32B0, ax
0x180040f17  call    cs:__imp_RegisterClipboardFormatA
0x180040f1d  mov     cs:word_1800A3270, ax
0x180040f24  add     rsp, 28h
0x180040f28  retn
```
