# CResponse::WriteBlocksResponse(CIsapiReqInfo *,ulong,_WSABUF *,ulong,char *,char *,char *)

- ea: `0x18005316c`
- end: `0x18005335a`
- name: `?WriteBlocksResponse@CResponse@@SAJPEAVCIsapiReqInfo@@KPEAU_WSABUF@@KPEAD22@Z`
- size: `494`
- prototype: `__int64 __fastcall(struct CIsapiReqInfo *this, unsigned int, struct _WSABUF *, unsigned int, char *, char *, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800482a8`

## callees

- `0x180017fc0`
- `0x180019090`
- `0x180050be4`
- `0x180051970`
- `0x180051e5c`
- `0x180051f40`
- `0x180052040`
- `0x18005316c`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800531b2`
- `msvcrt!_stricmp` at `0x1800531b2`
- `KERNEL32!HeapFree` at `0x180053317`
- `KERNEL32!HeapFree` at `0x18005332f`
- `KERNEL32!HeapFree` at `0x180053317`
- `KERNEL32!HeapFree` at `0x18005332f`
- `KERNEL32!GetLastError` at `0x1800532f0`
- `KERNEL32!GetLastError` at `0x1800532f0`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800531e3`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800531e3`

## pseudocode

```c
int __fastcall CResponse::WriteBlocksResponse(
        struct CIsapiReqInfo *this,
        unsigned int a2,
        struct _WSABUF *a3,
        unsigned int a4)
{
  int v4; // r14d
  __int64 v6; // rcx
  const char *v9; // rcx
  int result; // eax
  int v11; // esi
  int v12; // r14d
  char *v13; // rax
  char *v14; // rbx
  CResponseBufferSet *v15; // rcx
  _QWORD *v16; // rax
  unsigned int v17; // edx
  signed int v18; // edi
  char *ResponseMimeType; // rax
  unsigned int i; // esi
  __int64 v21; // rcx
  struct WSABUF_VECTORS *v22; // r9
  signed int LastError; // eax
  __int128 v24; // [rsp+30h] [rbp-51h] BYREF
  __int64 v25; // [rsp+40h] [rbp-41h]
  struct _HSE_SEND_HEADER_EX_INFO lpMem; // [rsp+48h] [rbp-39h] BYREF
  __int128 v27; // [rsp+68h] [rbp-19h]

  v4 = *((_DWORD *)this + 13);
  v6 = *((_QWORD *)this + 1);
  v24 = 0;
  v9 = *(const char **)(v6 + 104);
  v25 = 0;
  result = _stricmp(v9, "HEAD");
  v11 = result;
  v12 = v4 & 0x800;
  if ( v12 && !result )
    return result;
  memset(&lpMem, 0, sizeof(lpMem));
  v27 = 0;
  v13 = (char *)ALLOC_CACHE_HANDLER::Alloc(CResponseBufferSet::sm_pach);
  v14 = v13;
  if ( !v13 )
    return -2147024882;
  *((_DWORD *)v13 + 42) &= 0xFFFFFFFC;
  *(_QWORD *)v13 = 0;
  v15 = (CResponseBufferSet *)v13;
  *((_QWORD *)v13 + 1) = 0;
  *((_QWORD *)v13 + 2) = 0;
  v16 = v13 + 24;
  *((_DWORD *)v14 + 40) = 0;
  *((_QWORD *)v14 + 19) = v16;
  *((_DWORD *)v14 + 41) = 16;
  *v16 = 0;
  v18 = CResponseBufferSet::Init(v15, 0x400000u);
  if ( v18 >= 0 )
  {
    if ( v12 )
    {
LABEL_8:
      if ( v11 )
      {
        for ( i = 0; ; ++i )
        {
          v21 = *(_QWORD *)v14;
          if ( i >= a2 )
            break;
          v18 = CResponseBuffer::Write((CResponseBuffer *)v21, a3[i].buf, a3[i].len, 0, 0);
          if ( v18 < 0 )
            goto LABEL_18;
        }
        CResponseVector::GetVectors((CResponseVector *)(v21 + 8), (struct WSABUF_VECTORS *)&v24);
        v22 = (struct WSABUF_VECTORS *)&v24;
      }
      else
      {
        v22 = 0;
      }
      if ( !(unsigned int)CIsapiReqInfo::SendClientResponse(
                            this,
                            0,
                            (struct _HSE_SEND_ENTIRE_RESPONSE_INFO *)&lpMem,
                            v22,
                            0,
                            0) )
      {
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_18;
    }
    ResponseMimeType = (char *)GetResponseMimeType(this);
    v18 = CResponse::ConstructSimpleHeaders(
            &lpMem,
            a4,
            ResponseMimeType,
            "449 Retry with",
            "ms-echo-request: execute opaque=\"0\" location=\"BODY\"\r\n");
    if ( v18 >= 0 )
    {
      lpMem.fKeepConn = 1;
      goto LABEL_8;
    }
  }
LABEL_18:
  if ( lpMem.pszStatus )
    HeapFree(g_hDenaliHeap, 0, (LPVOID)lpMem.pszStatus);
  if ( lpMem.pszHeader )
    HeapFree(g_hDenaliHeap, 0, (LPVOID)lpMem.pszHeader);
  CResponseBufferSet::`scalar deleting destructor'((CResponseBufferSet *)v14, v17);
  return v18;
}

```

## disassembly

```asm
0x18005316c  mov     [rsp-8+arg_10], r8
0x180053171  push    rbp
0x180053172  push    rbx
0x180053173  push    rsi
0x180053174  push    rdi
0x180053175  push    r12
0x180053177  push    r13
0x180053179  push    r14
0x18005317b  push    r15
0x18005317d  lea     rbp, [rsp-7]
0x180053182  sub     rsp, 88h
0x180053189  mov     r14d, [rcx+34h]
0x18005318d  mov     r15, rcx
0x180053190  mov     rcx, [rcx+8]
0x180053194  mov     r13d, edx
0x180053197  xorps   xmm0, xmm0
0x18005319a  lea     rdx, aHead; "HEAD"
0x1800531a1  xor     eax, eax
0x1800531a3  mov     r12d, r9d
0x1800531a6  movups  [rbp+3Fh+var_90], xmm0
0x1800531aa  mov     rcx, [rcx+68h]; String1
0x1800531ae  mov     [rbp+3Fh+var_80], rax
0x1800531b2  call    cs:__imp__stricmp
0x1800531b8  xor     edi, edi
0x1800531ba  mov     esi, eax
0x1800531bc  and     r14d, 800h
0x1800531c3  jz      short loc_1800531CD
0x1800531c5  test    eax, eax
0x1800531c7  jz      loc_180053346
0x1800531cd  mov     rcx, cs:?sm_pach@CResponseBufferSet@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBufferSet::sm_pach
0x1800531d4  xorps   xmm0, xmm0
0x1800531d7  movups  xmmword ptr [rbp+3Fh+lpMem], xmm0
0x1800531db  movups  [rbp+3Fh+var_68], xmm0
0x1800531df  movups  [rbp+3Fh+var_58], xmm0
0x1800531e3  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800531e9  mov     rbx, rax
0x1800531ec  test    rax, rax
0x1800531ef  jz      loc_180053341
0x1800531f5  and     dword ptr [rax+0A8h], 0FFFFFFFCh
0x1800531fc  mov     edx, 400000h; unsigned int
0x180053201  mov     [rax], rdi
0x180053204  mov     rcx, rbx; this
0x180053207  mov     [rax+8], rdi
0x18005320b  mov     [rax+10h], rdi
0x18005320f  add     rax, 18h
0x180053213  mov     [rbx+0A0h], edi
0x180053219  mov     [rbx+98h], rax
0x180053220  mov     dword ptr [rbx+0A4h], 10h
0x18005322a  mov     [rax], rdi
0x18005322d  call    ?Init@CResponseBufferSet@@QEAAJK@Z; CResponseBufferSet::Init(ulong)
0x180053232  mov     edi, eax
0x180053234  test    eax, eax
0x180053236  js      loc_180053305
0x18005323c  test    r14d, r14d
0x18005323f  jnz     short loc_18005327C
0x180053241  mov     rcx, r15; this
0x180053244  call    ?GetResponseMimeType@@YAPEBDPEAVCIsapiReqInfo@@@Z; GetResponseMimeType(CIsapiReqInfo *)
0x180053249  lea     rcx, aMsEchoRequestE; "ms-echo-request: execute opaque=\"0\" l"...
0x180053250  mov     r8, rax; char *
0x180053253  mov     [rsp+0C0h+var_A0], rcx; char *
0x180053258  lea     r9, a449RetryWith; "449 Retry with"
0x18005325f  lea     rcx, [rbp+3Fh+lpMem]; struct _HSE_SEND_HEADER_EX_INFO *
0x180053263  mov     edx, r12d; unsigned int
0x180053266  call    ?ConstructSimpleHeaders@CResponse@@SAJPEAU_HSE_SEND_HEADER_EX_INFO@@KPEAD11@Z; CResponse::ConstructSimpleHeaders(_HSE_SEND_HEADER_EX_INFO *,ulong,char *,char *,char *)
0x18005326b  mov     edi, eax
0x18005326d  test    eax, eax
0x18005326f  js      loc_180053305
0x180053275  mov     dword ptr [rbp+3Fh+var_68+8], 1
0x18005327c  test    esi, esi
0x18005327e  jz      short loc_1800532C9
0x180053280  xor     esi, esi
0x180053282  mov     rcx, [rbx]; this
0x180053285  cmp     esi, r13d
0x180053288  jnb     short loc_1800532B6
0x18005328a  mov     rax, [rbp+3Fh+arg_10]
0x18005328e  xor     r9d, r9d; int
0x180053291  mov     edx, esi
0x180053293  add     rdx, rdx
0x180053296  mov     dword ptr [rsp+0C0h+var_A0], 0; int
0x18005329e  mov     r8d, [rax+rdx*8]; unsigned int
0x1800532a2  mov     rdx, [rax+rdx*8+8]; char *
0x1800532a7  call    ?Write@CResponseBuffer@@QEAAJPEADKHH@Z; CResponseBuffer::Write(char *,ulong,int,int)
0x1800532ac  mov     edi, eax
0x1800532ae  test    eax, eax
0x1800532b0  js      short loc_180053305
0x1800532b2  inc     esi
0x1800532b4  jmp     short loc_180053282
0x1800532b6  add     rcx, 8; this
0x1800532ba  lea     rdx, [rbp+3Fh+var_90]; struct WSABUF_VECTORS *
0x1800532be  call    ?GetVectors@CResponseVector@@QEAAXPEAUWSABUF_VECTORS@@@Z; CResponseVector::GetVectors(WSABUF_VECTORS *)
0x1800532c3  lea     r9, [rbp+3Fh+var_90]
0x1800532c7  jmp     short loc_1800532CC
0x1800532c9  xor     r9d, r9d; struct WSABUF_VECTORS *
0x1800532cc  mov     [rsp+0C0h+var_98], 0; void *
0x1800532d5  lea     r8, [rbp+3Fh+lpMem]; struct _HSE_SEND_ENTIRE_RESPONSE_INFO *
0x1800532d9  xor     edx, edx; int
0x1800532db  mov     [rsp+0C0h+var_A0], 0; void (*)(void *)
0x1800532e4  mov     rcx, r15; this
0x1800532e7  call    ?SendClientResponse@CIsapiReqInfo@@QEAAHHPEAU_HSE_SEND_ENTIRE_RESPONSE_INFO@@PEAUWSABUF_VECTORS@@P6AXPEAX@Z2@Z; CIsapiReqInfo::SendClientResponse(int,_HSE_SEND_ENTIRE_RESPONSE_INFO *,WSABUF_VECTORS *,void (*)(void *),void *)
0x1800532ec  test    eax, eax
0x1800532ee  jnz     short loc_180053305
0x1800532f0  call    cs:__imp_GetLastError
0x1800532f6  mov     edi, eax
0x1800532f8  test    eax, eax
0x1800532fa  jle     short loc_180053305
0x1800532fc  movzx   edi, ax
0x1800532ff  or      edi, 80070000h
0x180053305  mov     r8, [rbp+3Fh+lpMem]; lpMem
0x180053309  test    r8, r8
0x18005330c  jz      short loc_18005331D
0x18005330e  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180053315  xor     edx, edx; dwFlags
0x180053317  call    cs:__imp_HeapFree
0x18005331d  mov     r8, [rbp+3Fh+lpMem+8]; lpMem
0x180053321  test    r8, r8
0x180053324  jz      short loc_180053335
0x180053326  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005332d  xor     edx, edx; dwFlags
0x18005332f  call    cs:__imp_HeapFree
0x180053335  mov     rcx, rbx; this
0x180053338  call    ??_GCResponseBufferSet@@QEAAPEAXI@Z; CResponseBufferSet::`scalar deleting destructor'(uint)
0x18005333d  mov     eax, edi
0x18005333f  jmp     short loc_180053346
0x180053341  mov     eax, 8007000Eh
0x180053346  add     rsp, 88h
0x18005334d  pop     r15
0x18005334f  pop     r14
0x180053351  pop     r13
0x180053353  pop     r12
0x180053355  pop     rdi
0x180053356  pop     rsi
0x180053357  pop     rbx
0x180053358  pop     rbp
0x180053359  retn
```
