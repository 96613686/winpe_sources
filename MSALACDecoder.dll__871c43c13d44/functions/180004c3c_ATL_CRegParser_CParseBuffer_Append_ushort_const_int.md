# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180004c3c`
- end: `0x180004cf2`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057d0`

## callees

- `0x180004c3c`
- `0x180007274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004c8f`

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
0x180004c3c  push    rbx
0x180004c3e  push    rbp
0x180004c3f  push    rsi
0x180004c40  push    rdi
0x180004c41  sub     rsp, 28h
0x180004c45  mov     rdi, rcx
0x180004c48  mov     esi, r8d
0x180004c4b  lea     ecx, [r8+1]
0x180004c4f  mov     rbp, rdx
0x180004c52  add     ecx, [rdi]
0x180004c54  cmp     ecx, [rdi]
0x180004c56  jle     loc_180004CE7
0x180004c5c  cmp     ecx, r8d
0x180004c5f  jle     loc_180004CE7
0x180004c65  mov     ebx, [rdi+4]
0x180004c68  cmp     ecx, ebx
0x180004c6a  jl      short loc_180004CA1
0x180004c6c  cmp     ebx, 3FFFFFFFh
0x180004c72  jg      short loc_180004CE7
0x180004c74  add     ebx, ebx
0x180004c76  cmp     ecx, ebx
0x180004c78  jge     short loc_180004C6C
0x180004c7a  mov     eax, ebx
0x180004c7c  mov     ecx, 0FFFFFFFFh
0x180004c81  add     rax, rax
0x180004c84  cmp     rax, rcx
0x180004c87  ja      short loc_180004CE7
0x180004c89  mov     rcx, [rdi+8]; pv
0x180004c8d  mov     edx, eax; cb
0x180004c8f  call    cs:__imp_CoTaskMemRealloc
0x180004c95  test    rax, rax
0x180004c98  jz      short loc_180004CE7
0x180004c9a  mov     [rdi+8], rax
0x180004c9e  mov     [rdi+4], ebx
0x180004ca1  cmp     dword ptr [rdi], 0
0x180004ca4  jl      short loc_180004CE7
0x180004ca6  cmp     [rdi], ebx
0x180004ca8  jge     short loc_180004CE7
0x180004caa  mov     ecx, ebx
0x180004cac  sub     ecx, [rdi]
0x180004cae  cmp     ecx, ebx
0x180004cb0  jg      short loc_180004CE7
0x180004cb2  movsxd  rdx, ecx
0x180004cb5  lea     eax, [rsi+rsi]
0x180004cb8  movsxd  rcx, dword ptr [rdi]
0x180004cbb  add     rdx, rdx; void *
0x180004cbe  movsxd  r9, eax; void *
0x180004cc1  mov     r8, rbp; unsigned __int64
0x180004cc4  mov     rax, [rdi+8]
0x180004cc8  lea     rcx, [rax+rcx*2]; this
0x180004ccc  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180004cd1  add     [rdi], esi
0x180004cd3  movsxd  rdx, dword ptr [rdi]
0x180004cd6  xor     eax, eax
0x180004cd8  mov     rcx, [rdi+8]
0x180004cdc  mov     [rcx+rdx*2], ax
0x180004ce0  mov     eax, 1
0x180004ce5  jmp     short loc_180004CE9
0x180004ce7  xor     eax, eax
0x180004ce9  add     rsp, 28h
0x180004ced  pop     rdi
0x180004cee  pop     rsi
0x180004cef  pop     rbp
0x180004cf0  pop     rbx
0x180004cf1  retn
```
