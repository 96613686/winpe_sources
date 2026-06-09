# CMpeg2StatsCOM::CreateInstance(IUnknown *,long *)

- ea: `0x180011730`
- end: `0x1800117ea`
- name: `?CreateInstance@CMpeg2StatsCOM@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `186`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180011730`

## pseudocode

```c
struct IUnknown *__fastcall CMpeg2StatsCOM::CreateInstance(struct IUnknown *a1, int *a2)
{
  struct IUnknown *v4; // rax
  struct IUnknown *v5; // r8
  struct IUnknown *result; // rax

  v4 = (struct IUnknown *)operator new(0x88u);
  v5 = v4;
  if ( v4 )
  {
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    v4[3].lpVtbl = 0;
    v4[4].lpVtbl = 0;
    if ( a1 )
      v4 = a1;
    v5[6].lpVtbl = 0;
    v5[1].lpVtbl = (struct IUnknownVtbl *)v4;
    v5->lpVtbl = (struct IUnknownVtbl *)&CMpeg2StatsCOM::`vftable';
    v5[5].lpVtbl = (struct IUnknownVtbl *)&Mp2DemuxSec::CStatsMMSec::`vftable';
    LODWORD(v5[2].lpVtbl) = 0;
    v5[10].lpVtbl = 0;
    v5[11].lpVtbl = 0;
    LOBYTE(v5[12].lpVtbl) = 0;
    v5[13].lpVtbl = 0;
    v5[14].lpVtbl = 0;
    LODWORD(v5[15].lpVtbl) = 11;
    HIDWORD(v5[15].lpVtbl) = 18;
    LODWORD(v5[16].lpVtbl) = 19;
    HIDWORD(v5[16].lpVtbl) = 20;
  }
  else
  {
    v5 = 0;
  }
  result = v5;
  *a2 = v5 == 0 ? 0x8007000E : 0;
  return result;
}

```

## disassembly

```asm
0x180011730  mov     [rsp+arg_0], rbx
0x180011735  push    rdi
0x180011736  sub     rsp, 20h
0x18001173a  mov     rdi, rcx
0x18001173d  mov     rbx, rdx
0x180011740  mov     ecx, 88h; Size
0x180011745  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001174a  xor     ecx, ecx
0x18001174c  mov     r8, rax
0x18001174f  test    rax, rax
0x180011752  jz      short loc_1800117C7
0x180011754  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18001175b  test    rdi, rdi
0x18001175e  mov     [r8+18h], rcx
0x180011762  mov     [r8+20h], rcx
0x180011766  cmovnz  rax, rdi
0x18001176a  mov     [r8+30h], rcx
0x18001176e  mov     [r8+8], rax
0x180011772  lea     rax, ??_7CMpeg2StatsCOM@@6B@; const CMpeg2StatsCOM::`vftable'
0x180011779  mov     [r8], rax
0x18001177c  lea     rax, ??_7CStatsMMSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CStatsMMSec::`vftable'
0x180011783  mov     [r8+28h], rax
0x180011787  mov     [r8+10h], ecx
0x18001178b  mov     [r8+50h], rcx
0x18001178f  mov     [r8+58h], rcx
0x180011793  mov     [r8+60h], cl
0x180011797  mov     [r8+68h], rcx
0x18001179b  mov     [r8+70h], rcx
0x18001179f  mov     dword ptr [r8+78h], 0Bh
0x1800117a7  mov     dword ptr [r8+7Ch], 12h
0x1800117af  mov     dword ptr [r8+80h], 13h
0x1800117ba  mov     dword ptr [r8+84h], 14h
0x1800117c5  jmp     short loc_1800117CA
0x1800117c7  mov     r8, rcx
0x1800117ca  mov     rcx, r8
0x1800117cd  mov     rax, r8
0x1800117d0  neg     rcx
0x1800117d3  sbb     edx, edx
0x1800117d5  not     edx
0x1800117d7  and     edx, 8007000Eh
0x1800117dd  mov     [rbx], edx
0x1800117df  mov     rbx, [rsp+28h+arg_0]
0x1800117e4  add     rsp, 20h
0x1800117e8  pop     rdi
0x1800117e9  retn
```
