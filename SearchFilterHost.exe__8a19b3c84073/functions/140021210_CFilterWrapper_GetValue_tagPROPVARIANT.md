# CFilterWrapper::GetValue(tagPROPVARIANT * *)

- ea: `0x140021210`
- end: `0x1400212c2`
- name: `?GetValue@CFilterWrapper@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(CFilterWrapper *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001fdfc`
- `0x140021210`
- `0x140024efc`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140021261`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140021261`

## pseudocode

```c
__int64 __fastcall CFilterWrapper::GetValue(LARGE_INTEGER *this, struct tagPROPVARIANT **a2)
{
  LARGE_INTEGER v4; // rcx
  unsigned int v5; // edi
  struct tagPROPVARIANT *v6; // rsi
  __int64 CurrentProcessTime; // rax

  *a2 = 0;
  CFilterProcessBackoffCtrl::Wait((CFilterProcessBackoffCtrl *)&this[20]);
  v4 = this[6];
  if ( v4.QuadPart )
  {
    if ( this[10].HighPart )
    {
      v6 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
      if ( v6 )
      {
        *(_OWORD *)&v6->vt = 0;
        v6->bstrblobVal.pData = 0;
        v5 = 0;
        v6->vt = 21;
        if ( LOBYTE(this[12].LowPart) )
        {
          CurrentProcessTime = CTimeLapse::GetCurrentProcessTime((CTimeLapse *)&this[12]);
          if ( (this[15].LowPart & 0x80000000) == 0 )
          {
            this[14].QuadPart += CurrentProcessTime - this[13].QuadPart;
            this[13].QuadPart = CurrentProcessTime;
          }
        }
        v6->hVal = this[14];
        *a2 = v6;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (*(unsigned int (__fastcall **)(LARGE_INTEGER, struct tagPROPVARIANT **))(*(_QWORD *)v4.QuadPart + 48LL))(
               v4,
               a2);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x140021210  push    rbx
0x140021212  push    rsi
0x140021213  push    rdi
0x140021214  push    r14
0x140021216  sub     rsp, 28h
0x14002121a  mov     rbx, rcx
0x14002121d  mov     qword ptr [rdx], 0
0x140021224  add     rcx, 0A0h; this
0x14002122b  mov     r14, rdx
0x14002122e  call    ?Wait@CFilterProcessBackoffCtrl@@QEAAXXZ; CFilterProcessBackoffCtrl::Wait(void)
0x140021233  mov     rcx, [rbx+30h]
0x140021237  test    rcx, rcx
0x14002123a  jnz     short loc_140021243
0x14002123c  mov     edi, 80004003h
0x140021241  jmp     short loc_1400212B6
0x140021243  cmp     dword ptr [rbx+54h], 0
0x140021247  jnz     short loc_14002125C
0x140021249  mov     rax, [rcx]
0x14002124c  mov     rdx, r14
0x14002124f  mov     rax, [rax+30h]
0x140021253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021258  mov     edi, eax
0x14002125a  jmp     short loc_1400212B6
0x14002125c  mov     ecx, 18h; cb
0x140021261  call    cs:__imp_CoTaskMemAlloc
0x140021267  mov     rsi, rax
0x14002126a  test    rax, rax
0x14002126d  jz      short loc_1400212B1
0x14002126f  xor     eax, eax
0x140021271  xorps   xmm0, xmm0
0x140021274  movups  xmmword ptr [rsi], xmm0
0x140021277  mov     [rsi+10h], rax
0x14002127b  xor     edi, edi
0x14002127d  mov     word ptr [rsi], 15h
0x140021282  cmp     [rbx+60h], al
0x140021285  jz      short loc_1400212A4
0x140021287  lea     rcx, [rbx+60h]; this
0x14002128b  call    ?GetCurrentProcessTime@CTimeLapse@@AEAA_KXZ; CTimeLapse::GetCurrentProcessTime(void)
0x140021290  cmp     [rbx+78h], edi
0x140021293  jl      short loc_1400212A4
0x140021295  mov     rcx, rax
0x140021298  sub     rcx, [rbx+68h]
0x14002129c  add     [rbx+70h], rcx
0x1400212a0  mov     [rbx+68h], rax
0x1400212a4  mov     rax, [rbx+70h]
0x1400212a8  mov     [rsi+8], rax
0x1400212ac  mov     [r14], rsi
0x1400212af  jmp     short loc_1400212B6
0x1400212b1  mov     edi, 8007000Eh
0x1400212b6  mov     eax, edi
0x1400212b8  add     rsp, 28h
0x1400212bc  pop     r14
0x1400212be  pop     rdi
0x1400212bf  pop     rsi
0x1400212c0  pop     rbx
0x1400212c1  retn
```
