# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18001faac`
- end: `0x18001fb62`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020b20`

## callees

- `0x18001faac`
- `0x180022644`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001faff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001faff`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  unsigned __int64 v12; // [rsp+20h] [rbp-28h]

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 < v7 )
    {
LABEL_9:
      if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
      {
        v10 = v7 - *(_DWORD *)this;
        if ( v10 <= v7 )
        {
          ATL::Checked::memcpy_s(
            (ATL::Checked *)(*((_QWORD *)this + 1) + 2LL * *(int *)this),
            (void *)(2LL * v10),
            (unsigned __int64)a2,
            (const void *)(2 * a3),
            v12);
          *(_DWORD *)this += a3;
          *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
          return 1;
        }
      }
    }
    else
    {
      while ( v7 <= 0x3FFFFFFF )
      {
        v7 *= 2;
        if ( v6 < v7 )
        {
          v8 = 2LL * (unsigned int)v7;
          if ( v8 <= 0xFFFFFFFF )
          {
            v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
            if ( v9 )
            {
              *((_QWORD *)this + 1) = v9;
              *((_DWORD *)this + 1) = v7;
              goto LABEL_9;
            }
          }
          return 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001faac  push    rbx
0x18001faae  push    rbp
0x18001faaf  push    rsi
0x18001fab0  push    rdi
0x18001fab1  sub     rsp, 28h
0x18001fab5  mov     rdi, rcx
0x18001fab8  mov     esi, r8d
0x18001fabb  lea     ecx, [r8+1]
0x18001fabf  mov     rbp, rdx
0x18001fac2  add     ecx, [rdi]
0x18001fac4  cmp     ecx, [rdi]
0x18001fac6  jle     loc_18001FB57
0x18001facc  cmp     ecx, r8d
0x18001facf  jle     loc_18001FB57
0x18001fad5  mov     ebx, [rdi+4]
0x18001fad8  cmp     ecx, ebx
0x18001fada  jl      short loc_18001FB11
0x18001fadc  cmp     ebx, 3FFFFFFFh
0x18001fae2  jg      short loc_18001FB57
0x18001fae4  add     ebx, ebx
0x18001fae6  cmp     ecx, ebx
0x18001fae8  jge     short loc_18001FADC
0x18001faea  mov     eax, ebx
0x18001faec  mov     ecx, 0FFFFFFFFh
0x18001faf1  add     rax, rax
0x18001faf4  cmp     rax, rcx
0x18001faf7  ja      short loc_18001FB57
0x18001faf9  mov     rcx, [rdi+8]; pv
0x18001fafd  mov     edx, eax; cb
0x18001faff  call    cs:__imp_CoTaskMemRealloc
0x18001fb05  test    rax, rax
0x18001fb08  jz      short loc_18001FB57
0x18001fb0a  mov     [rdi+8], rax
0x18001fb0e  mov     [rdi+4], ebx
0x18001fb11  cmp     dword ptr [rdi], 0
0x18001fb14  jl      short loc_18001FB57
0x18001fb16  cmp     [rdi], ebx
0x18001fb18  jge     short loc_18001FB57
0x18001fb1a  mov     ecx, ebx
0x18001fb1c  sub     ecx, [rdi]
0x18001fb1e  cmp     ecx, ebx
0x18001fb20  jg      short loc_18001FB57
0x18001fb22  movsxd  rdx, ecx
0x18001fb25  lea     eax, [rsi+rsi]
0x18001fb28  movsxd  rcx, dword ptr [rdi]
0x18001fb2b  add     rdx, rdx; void *
0x18001fb2e  movsxd  r9, eax; void *
0x18001fb31  mov     r8, rbp; unsigned __int64
0x18001fb34  mov     rax, [rdi+8]
0x18001fb38  lea     rcx, [rax+rcx*2]; this
0x18001fb3c  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18001fb41  add     [rdi], esi
0x18001fb43  movsxd  rdx, dword ptr [rdi]
0x18001fb46  xor     eax, eax
0x18001fb48  mov     rcx, [rdi+8]
0x18001fb4c  mov     [rcx+rdx*2], ax
0x18001fb50  mov     eax, 1
0x18001fb55  jmp     short loc_18001FB59
0x18001fb57  xor     eax, eax
0x18001fb59  add     rsp, 28h
0x18001fb5d  pop     rdi
0x18001fb5e  pop     rsi
0x18001fb5f  pop     rbp
0x18001fb60  pop     rbx
0x18001fb61  retn
```
