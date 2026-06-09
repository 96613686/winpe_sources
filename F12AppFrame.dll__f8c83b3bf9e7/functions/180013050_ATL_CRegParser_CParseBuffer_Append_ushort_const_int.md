# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180013050`
- end: `0x180013106`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800155a0`

## callees

- `0x180005704`
- `0x180013050`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x1800130a3`
- `ole32!CoTaskMemRealloc` at `0x1800130a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013050  push    rbx
0x180013052  push    rbp
0x180013053  push    rsi
0x180013054  push    rdi
0x180013055  sub     rsp, 28h
0x180013059  mov     rdi, rcx
0x18001305c  mov     esi, r8d
0x18001305f  lea     ecx, [r8+1]
0x180013063  mov     rbp, rdx
0x180013066  add     ecx, [rdi]
0x180013068  cmp     ecx, [rdi]
0x18001306a  jle     loc_1800130FB
0x180013070  cmp     ecx, r8d
0x180013073  jle     loc_1800130FB
0x180013079  mov     ebx, [rdi+4]
0x18001307c  cmp     ecx, ebx
0x18001307e  jl      short loc_1800130B5
0x180013080  cmp     ebx, 3FFFFFFFh
0x180013086  jg      short loc_1800130FB
0x180013088  add     ebx, ebx
0x18001308a  cmp     ecx, ebx
0x18001308c  jge     short loc_180013080
0x18001308e  mov     eax, ebx
0x180013090  mov     ecx, 0FFFFFFFFh
0x180013095  add     rax, rax
0x180013098  cmp     rax, rcx
0x18001309b  ja      short loc_1800130FB
0x18001309d  mov     rcx, [rdi+8]; pv
0x1800130a1  mov     edx, eax; cb
0x1800130a3  call    cs:__imp_CoTaskMemRealloc
0x1800130a9  test    rax, rax
0x1800130ac  jz      short loc_1800130FB
0x1800130ae  mov     [rdi+8], rax
0x1800130b2  mov     [rdi+4], ebx
0x1800130b5  cmp     dword ptr [rdi], 0
0x1800130b8  jl      short loc_1800130FB
0x1800130ba  cmp     [rdi], ebx
0x1800130bc  jge     short loc_1800130FB
0x1800130be  mov     ecx, ebx
0x1800130c0  sub     ecx, [rdi]
0x1800130c2  cmp     ecx, ebx
0x1800130c4  jg      short loc_1800130FB
0x1800130c6  movsxd  rdx, ecx
0x1800130c9  lea     eax, [rsi+rsi]
0x1800130cc  movsxd  rcx, dword ptr [rdi]
0x1800130cf  add     rdx, rdx; void *
0x1800130d2  movsxd  r9, eax; void *
0x1800130d5  mov     r8, rbp; unsigned __int64
0x1800130d8  mov     rax, [rdi+8]
0x1800130dc  lea     rcx, [rax+rcx*2]; this
0x1800130e0  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1800130e5  add     [rdi], esi
0x1800130e7  movsxd  rdx, dword ptr [rdi]
0x1800130ea  xor     eax, eax
0x1800130ec  mov     rcx, [rdi+8]
0x1800130f0  mov     [rcx+rdx*2], ax
0x1800130f4  mov     eax, 1
0x1800130f9  jmp     short loc_1800130FD
0x1800130fb  xor     eax, eax
0x1800130fd  add     rsp, 28h
0x180013101  pop     rdi
0x180013102  pop     rsi
0x180013103  pop     rbp
0x180013104  pop     rbx
0x180013105  retn
```
