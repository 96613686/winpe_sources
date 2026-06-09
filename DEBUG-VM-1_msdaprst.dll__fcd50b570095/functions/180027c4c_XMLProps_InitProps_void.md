# XMLProps::_InitProps(void)

- ea: `0x180027c4c`
- end: `0x180027eb6`
- name: `?_InitProps@XMLProps@@CAXXZ`
- size: `618`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001edac`
- `0x1800272f0`

## pseudocode

```c
void XMLProps::_InitProps(void)
{
  LODWORD(XMLProps::m_rgXMLProps) = 34;
  dword_180045598 = 0;
  word_1800455B0 = 0;
  word_1800455C8 = -1;
  xmmword_18004555C[0] = (__int128)DBPROPSET_ROWSET;
  LODWORD(XMLProps::m_rgRSAttr) = 4;
  dword_180045718 = 4;
  LODWORD(XMLProps::m_rgTags) = 370480147;
  word_1800455A8 = 11;
  dword_180045720 = 14;
  dword_1800456E8 = 14;
  dword_1800456C4 = 5;
  word_1800455C0 = 11;
  dword_18004570C = 5;
  XMLProps::m_rgPropSets = (struct tagDBPROPIDSET near *)&XMLProps::m_rgXMLProps;
  dword_180045714 = 11;
  qword_180045570 = (__int64)&dword_18004570C;
  XMLProps::m_rgTagSets = &XMLProps::m_rgTags;
  qword_180045538 = (__int64)&XMLProps::m_rgTags + 3;
  dword_1800456DC = 11;
  XMLProps::m_rgRSAttrSets = &XMLProps::m_rgRSAttr;
  LOWORD(XMLProps::m_rgDefaults) = 3;
  dword_180045704 = 127;
  dword_180045708 = 134;
  dword_1800456C8 = 6;
  dword_1800456CC = 7;
  word_1800455D8 = 3;
  dword_1800455E0 = 2;
  dword_180045710 = 19;
  dword_1800456F4 = 437852183;
  dword_1800456D0 = 8;
  word_1800455F0 = 3;
  dword_1800455F8 = 1;
  dword_1800456D4 = 9;
  word_180045608 = 3;
  dword_180045610 = 1;
  dword_1800456D8 = 10;
  word_180045620 = 3;
  dword_180045628 = 15;
  dword_18004571C = 13;
  word_180045638 = 8;
  qword_180045640 = (__int64)&strIn;
  dword_1800456F8 = 505224219;
  dword_1800456E0 = 12;
  word_180045650 = 8;
  qword_180045658 = (__int64)&strIn;
  dword_180045724 = 15;
  dword_1800456E4 = 13;
  word_180045668 = 8;
  qword_180045670 = (__int64)&strIn;
  dword_180045728 = 16;
  word_180045680 = 8;
  qword_180045688 = (__int64)&strIn;
  dword_18004572C = 18;
  dword_1800456EC = 15;
  word_180045698 = 8;
  qword_1800456A0 = (__int64)&strIn;
  dword_180045558 = 3;
  dword_180045578 = 9;
  xmmword_18004557C = (__int128)DBPROPSET_ADC;
  qword_1800456B8 = (__int64)&dword_1800456CC;
  XMLProps::m_rgDefaultSets = &XMLProps::m_rgDefaults;
  qword_180045548 = (__int64)&word_1800455D8;
  XMLProps::m_fInitialized = 1;
}

```

## disassembly

```asm
0x180027c4c  mov     [rsp+arg_0], rbx
0x180027c51  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180027c58  xor     eax, eax
0x180027c5a  mov     cs:?m_rgXMLProps@XMLProps@@0PAKA, 22h ; '"'; ulong near * XMLProps::m_rgXMLProps
0x180027c64  mov     cs:dword_180045598, eax
0x180027c6a  mov     r8d, 4
0x180027c70  mov     cs:word_1800455B0, ax
0x180027c77  or      eax, 0FFFFFFFFh
0x180027c7a  mov     cs:word_1800455C8, ax
0x180027c81  movdqu  cs:xmmword_18004555C, xmm0
0x180027c89  lea     ebx, [r8-1]
0x180027c8d  mov     cs:?m_rgRSAttr@XMLProps@@0PAW4ROWSETATTRIBUTES@@A, r8d; ROWSETATTRIBUTES near * XMLProps::m_rgRSAttr
0x180027c94  movups  xmm0, xmmword ptr cs:?DBPROPSET_ADC@@3U_GUID@@B.Data1; _GUID const DBPROPSET_ADC ...
0x180027c9b  lea     r9d, [r8+4]
0x180027c9f  mov     cs:dword_180045718, r8d
0x180027ca6  lea     edx, [rbx+8]
0x180027ca9  mov     cs:?m_rgTags@XMLProps@@0PAEA, 16151413h; uchar near * XMLProps::m_rgTags
0x180027cb3  lea     eax, [rbx+0Bh]
0x180027cb6  mov     cs:word_1800455A8, dx
0x180027cbd  mov     cs:dword_180045720, eax
0x180027cc3  lea     ecx, [rbx+2]
0x180027cc6  mov     cs:dword_1800456E8, eax
0x180027ccc  lea     r11d, [r8-3]
0x180027cd0  lea     r10d, [r8+5]
0x180027cd4  mov     cs:dword_1800456C4, ecx
0x180027cda  lea     r8d, [rbx+0Ch]
0x180027cde  mov     cs:word_1800455C0, dx
0x180027ce5  lea     rax, ?m_rgXMLProps@XMLProps@@0PAKA; ulong near * XMLProps::m_rgXMLProps
0x180027cec  mov     cs:dword_18004570C, ecx
0x180027cf2  mov     cs:?m_rgPropSets@XMLProps@@0PAUtagDBPROPIDSET@@A, rax; tagDBPROPIDSET near * XMLProps::m_rgPropSets
0x180027cf9  lea     ecx, [rbx+0Ah]
0x180027cfc  lea     rax, dword_18004570C
0x180027d03  mov     cs:dword_180045714, edx
0x180027d09  mov     cs:qword_180045570, rax
0x180027d10  lea     rax, ?m_rgTags@XMLProps@@0PAEA; uchar near * XMLProps::m_rgTags
0x180027d17  mov     cs:?m_rgTagSets@XMLProps@@0PAPEAEA, rax; uchar * near * XMLProps::m_rgTagSets
0x180027d1e  lea     rax, ?m_rgTags@XMLProps@@0PAEA+3; uchar near * XMLProps::m_rgTags
0x180027d25  mov     cs:qword_180045538, rax
0x180027d2c  lea     rax, ?m_rgRSAttr@XMLProps@@0PAW4ROWSETATTRIBUTES@@A; ROWSETATTRIBUTES near * XMLProps::m_rgRSAttr
0x180027d33  mov     cs:dword_1800456DC, edx
0x180027d39  lea     rdx, strIn
0x180027d40  mov     cs:?m_rgRSAttrSets@XMLProps@@0PAPEAW4ROWSETATTRIBUTES@@A, rax; ROWSETATTRIBUTES * near * XMLProps::m_rgRSAttrSets
0x180027d47  lea     rax, dword_1800456CC
0x180027d4e  mov     cs:?m_rgDefaults@XMLProps@@0PAUtagVARIANT@@A, bx; tagVARIANT near * XMLProps::m_rgDefaults
0x180027d55  mov     cs:dword_180045704, 7Fh
0x180027d5f  mov     cs:dword_180045708, 86h
0x180027d69  mov     cs:dword_1800456C8, 6
0x180027d73  mov     cs:dword_1800456CC, 7
0x180027d7d  mov     cs:word_1800455D8, bx
0x180027d84  mov     cs:dword_1800455E0, 2
0x180027d8e  mov     cs:dword_180045710, 13h
0x180027d98  mov     cs:dword_1800456F4, 1A191817h
0x180027da2  mov     cs:dword_1800456D0, r9d
0x180027da9  mov     cs:word_1800455F0, bx
0x180027db0  mov     cs:dword_1800455F8, r11d
0x180027db7  mov     cs:dword_1800456D4, r10d
0x180027dbe  mov     cs:word_180045608, bx
0x180027dc5  mov     cs:dword_180045610, r11d
0x180027dcc  mov     cs:dword_1800456D8, 0Ah
0x180027dd6  mov     cs:word_180045620, bx
0x180027ddd  mov     cs:dword_180045628, r8d
0x180027de4  mov     cs:dword_18004571C, ecx
0x180027dea  mov     cs:word_180045638, r9w
0x180027df2  mov     cs:qword_180045640, rdx
0x180027df9  mov     cs:dword_1800456F8, 1E1D1C1Bh
0x180027e03  mov     cs:dword_1800456E0, 0Ch
0x180027e0d  mov     cs:word_180045650, r9w
0x180027e15  mov     cs:qword_180045658, rdx
0x180027e1c  mov     cs:dword_180045724, r8d
0x180027e23  mov     cs:dword_1800456E4, ecx
0x180027e29  mov     cs:word_180045668, r9w
0x180027e31  mov     cs:qword_180045670, rdx
0x180027e38  mov     cs:dword_180045728, 10h
0x180027e42  mov     cs:word_180045680, r9w
0x180027e4a  mov     cs:qword_180045688, rdx
0x180027e51  mov     cs:dword_18004572C, 12h
0x180027e5b  mov     cs:dword_1800456EC, r8d
0x180027e62  mov     cs:word_180045698, r9w
0x180027e6a  mov     cs:qword_1800456A0, rdx
0x180027e71  mov     cs:dword_180045558, ebx
0x180027e77  mov     cs:dword_180045578, r10d
0x180027e7e  movdqu  cs:xmmword_18004557C, xmm0
0x180027e86  mov     rbx, [rsp+arg_0]
0x180027e8b  mov     cs:qword_1800456B8, rax
0x180027e92  lea     rax, ?m_rgDefaults@XMLProps@@0PAUtagVARIANT@@A; tagVARIANT near * XMLProps::m_rgDefaults
0x180027e99  mov     cs:?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A, rax; tagVARIANT * near * XMLProps::m_rgDefaultSets
0x180027ea0  lea     rax, word_1800455D8
0x180027ea7  mov     cs:qword_180045548, rax
0x180027eae  mov     cs:?m_fInitialized@XMLProps@@0KA, r11d; ulong XMLProps::m_fInitialized
0x180027eb5  retn
```
