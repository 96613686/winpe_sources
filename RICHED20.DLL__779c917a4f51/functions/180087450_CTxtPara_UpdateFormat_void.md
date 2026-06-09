# CTxtPara::UpdateFormat(void)

- ea: `0x180087450`
- end: `0x1800874ce`
- name: `?UpdateFormat@CTxtPara@@AEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(CTxtPara *__hidden this)`
- caller_count: `12`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180084610`
- `0x180084780`
- `0x180084828`
- `0x180084a20`
- `0x180084c10`
- `0x180085000`
- `0x1800853e8`
- `0x180085670`
- `0x180085a40`
- `0x180085d40`
- `0x180086470`
- `0x1800869b0`

## callees

- `0x180044ee0`
- `0x180049704`
- `0x180087450`
- `0x1800910fe`

## pseudocode

```c
__int64 __fastcall CTxtPara::UpdateFormat(CTxtPara *this)
{
  CTxtRange *v2; // rcx
  const int *v4; // rax
  size_t v5; // r9

  v2 = (CTxtRange *)*((_QWORD *)this + 2);
  if ( v2 && (*((_BYTE *)this + 84) & 2) == 0 )
  {
    if ( !*((_QWORD *)v2 + 6) )
    {
      *((_DWORD *)this + 20) = 0;
      return 2147746303LL;
    }
    *((_DWORD *)this + 20) = CTxtRange::GetParaFormat(v2, (CTxtPara *)((char *)this + 24), 0);
    if ( *((__int16 *)this + 21) >= 0 )
    {
      v4 = CTabsArray::Deref(qword_1800A41E0, *((__int16 *)this + 21));
      memmove_0((char *)this + 88, v4, v5);
      *((_WORD *)this + 21) = -1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180087450  mov     [rsp+arg_0], rbx
0x180087455  push    rdi
0x180087456  sub     rsp, 20h
0x18008745a  mov     rbx, rcx
0x18008745d  xor     edi, edi
0x18008745f  mov     rcx, [rcx+10h]; this
0x180087463  test    rcx, rcx
0x180087466  jz      short loc_1800874C1
0x180087468  test    byte ptr [rbx+54h], 2
0x18008746c  jnz     short loc_1800874C1
0x18008746e  cmp     [rcx+30h], rdi
0x180087472  jnz     short loc_18008747E
0x180087474  mov     [rbx+50h], edi
0x180087477  mov     eax, 800401FFh
0x18008747c  jmp     short loc_1800874C3
0x18008747e  lea     rdx, [rbx+18h]; struct CParaFormat *
0x180087482  xor     r8d, r8d; unsigned int
0x180087485  call    ?GetParaFormat@CTxtRange@@QEBAKPEAVCParaFormat@@K@Z; CTxtRange::GetParaFormat(CParaFormat *,ulong)
0x18008748a  mov     [rbx+50h], eax
0x18008748d  cmp     [rbx+2Ah], di
0x180087491  jl      short loc_1800874C1
0x180087493  movzx   r9d, byte ptr [rbx+29h]
0x180087498  movsx   edx, word ptr [rbx+2Ah]; int
0x18008749c  mov     rcx, cs:qword_1800A41E0; this
0x1800874a3  shl     r9, 2
0x1800874a7  call    ?Deref@CTabsArray@@QEBAPEBJJ@Z; CTabsArray::Deref(long)
0x1800874ac  mov     rdx, rax; Src
0x1800874af  lea     rcx, [rbx+58h]; void *
0x1800874b3  mov     r8, r9; Size
0x1800874b6  call    memmove_0
0x1800874bb  mov     word ptr [rbx+2Ah], 0FFFFh
0x1800874c1  xor     eax, eax
0x1800874c3  mov     rbx, [rsp+28h+arg_0]
0x1800874c8  add     rsp, 20h
0x1800874cc  pop     rdi
0x1800874cd  retn
```
