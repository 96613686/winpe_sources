# CBinding::CBinding(CServerContext *,ushort const *,void *,IClassAccess *,long,long *)

- ea: `0x1800245f0`
- end: `0x1800246f7`
- name: `??0CBinding@@QEAA@PEAVCServerContext@@PEBGPEAXPEAUIClassAccess@@JPEAJ@Z`
- size: `263`
- prototype: `CBinding *__fastcall(CBinding *this, struct CServerContext *, const unsigned __int16 *, void *, struct IClassAccess *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c84c`

## callees

- `0x180002aa0`
- `0x1800245f0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246ac`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800246a2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800246a2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002467f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002467f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002465a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002468b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002465a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002468b`

## pseudocode

```c
CBinding *__fastcall CBinding::CBinding(
        CBinding *this,
        struct CServerContext *a2,
        const unsigned __int16 *a3,
        void *a4,
        struct IClassAccess *a5,
        int a6,
        int *a7)
{
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned __int16 *v13; // rax
  int v14; // eax
  SIZE_T LengthSid; // rsi
  HLOCAL v16; // rax
  signed int LastError; // eax

  *a7 = -2147024882;
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 6) = a6;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
  }
  else
  {
    LODWORD(v10) = 0;
  }
  v11 = (unsigned int)(v10 + 1);
  v12 = v11;
  v13 = (unsigned __int16 *)LocalAlloc(0, 2 * v11);
  *(_QWORD *)this = v13;
  if ( v13 )
  {
    v14 = StringCchCopyW(v13, v12, a3);
    *a7 = v14;
    if ( v14 >= 0 )
    {
      LengthSid = GetLengthSid(a4);
      v16 = LocalAlloc(0, LengthSid);
      *((_QWORD *)this + 4) = v16;
      if ( v16 )
      {
        if ( CopySid(LengthSid, v16, a4) )
        {
          *a7 = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          *a7 = LastError;
        }
      }
    }
  }
  if ( *a7 >= 0 && a5 )
  {
    *((_QWORD *)this + 2) = a5;
    (*(void (__fastcall **)(struct IClassAccess *))(*(_QWORD *)a5 + 8LL))(a5);
  }
  return this;
}

```

## disassembly

```asm
0x1800245f0  push    rbx
0x1800245f2  push    rbp
0x1800245f3  push    rsi
0x1800245f4  push    rdi
0x1800245f5  push    r14
0x1800245f7  push    r15
0x1800245f9  sub     rsp, 28h
0x1800245fd  mov     rdi, [rsp+58h+arg_30]
0x180024605  xorps   xmm0, xmm0
0x180024608  mov     eax, [rsp+58h+arg_28]
0x18002460f  xor     r15d, r15d
0x180024612  mov     rbp, r9
0x180024615  mov     rsi, r8
0x180024618  mov     rbx, rcx
0x18002461b  mov     dword ptr [rdi], 8007000Eh
0x180024621  movups  xmmword ptr [rcx], xmm0
0x180024624  movups  xmmword ptr [rcx+10h], xmm0
0x180024628  movups  xmmword ptr [rcx+20h], xmm0
0x18002462c  mov     [rcx+30h], r15
0x180024630  mov     [rcx+38h], r15
0x180024634  mov     [rcx+18h], eax
0x180024637  test    r8, r8
0x18002463a  jnz     short loc_180024641
0x18002463c  mov     eax, r15d
0x18002463f  jmp     short loc_18002464F
0x180024641  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024645  inc     rax
0x180024648  cmp     [r8+rax*2], r15w
0x18002464d  jnz     short loc_180024645
0x18002464f  inc     eax
0x180024651  xor     ecx, ecx; uFlags
0x180024653  mov     r14d, eax
0x180024656  lea     rdx, [rax+rax]; uBytes
0x18002465a  call    cs:__imp_LocalAlloc
0x180024660  mov     [rbx], rax
0x180024663  test    rax, rax
0x180024666  jz      short loc_1800246C5
0x180024668  mov     r8, rsi; unsigned __int16 *
0x18002466b  mov     edx, r14d; unsigned __int64
0x18002466e  mov     rcx, rax; unsigned __int16 *
0x180024671  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024676  mov     [rdi], eax
0x180024678  test    eax, eax
0x18002467a  js      short loc_1800246C5
0x18002467c  mov     rcx, rbp; pSid
0x18002467f  call    cs:__imp_GetLengthSid
0x180024685  mov     edx, eax; uBytes
0x180024687  xor     ecx, ecx; uFlags
0x180024689  mov     esi, eax
0x18002468b  call    cs:__imp_LocalAlloc
0x180024691  mov     [rbx+20h], rax
0x180024695  test    rax, rax
0x180024698  jz      short loc_1800246C5
0x18002469a  mov     r8, rbp; pSourceSid
0x18002469d  mov     rdx, rax; pDestinationSid
0x1800246a0  mov     ecx, esi; nDestinationSidLength
0x1800246a2  call    cs:__imp_CopySid
0x1800246a8  test    eax, eax
0x1800246aa  jnz     short loc_1800246C2
0x1800246ac  call    cs:__imp_GetLastError
0x1800246b2  test    eax, eax
0x1800246b4  jle     short loc_1800246BE
0x1800246b6  movzx   eax, ax
0x1800246b9  or      eax, 80070000h
0x1800246be  mov     [rdi], eax
0x1800246c0  jmp     short loc_1800246C5
0x1800246c2  mov     [rdi], r15d
0x1800246c5  cmp     [rdi], r15d
0x1800246c8  jl      short loc_1800246E7
0x1800246ca  mov     rcx, [rsp+58h+arg_20]
0x1800246d2  test    rcx, rcx
0x1800246d5  jz      short loc_1800246E7
0x1800246d7  mov     [rbx+10h], rcx
0x1800246db  mov     rax, [rcx]
0x1800246de  mov     rax, [rax+8]
0x1800246e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246e7  mov     rax, rbx
0x1800246ea  add     rsp, 28h
0x1800246ee  pop     r15
0x1800246f0  pop     r14
0x1800246f2  pop     rdi
0x1800246f3  pop     rsi
0x1800246f4  pop     rbp
0x1800246f5  pop     rbx
0x1800246f6  retn
```
