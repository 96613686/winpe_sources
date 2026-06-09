# CResponse::StaticWrite(CIsapiReqInfo *,char *,ulong,CTemplate *)

- ea: `0x180052ab0`
- end: `0x180052ca9`
- name: `?StaticWrite@CResponse@@SAJPEAVCIsapiReqInfo@@PEADKPEAVCTemplate@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(struct CIsapiReqInfo *this, char *, unsigned int, struct CTemplate *)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180042114`
- `0x18004311c`
- `0x180053360`

## callees

- `0x180017fc0`
- `0x180019090`
- `0x180050be4`
- `0x180051970`
- `0x180051e5c`
- `0x180051f40`
- `0x180052040`
- `0x180052ab0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180052af6`
- `msvcrt!_stricmp` at `0x180052af6`
- `KERNEL32!HeapFree` at `0x180052c66`
- `KERNEL32!HeapFree` at `0x180052c7e`
- `KERNEL32!HeapFree` at `0x180052c66`
- `KERNEL32!HeapFree` at `0x180052c7e`
- `KERNEL32!GetLastError` at `0x180052c3f`
- `KERNEL32!GetLastError` at `0x180052c3f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180052b28`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180052b28`

## pseudocode

```c
int __fastcall CResponse::StaticWrite(struct CIsapiReqInfo *this, char *a2, int a3, struct CTemplate *a4)
{
  int v4; // r12d
  __int64 v6; // rcx
  __int64 v8; // rsi
  int result; // eax
  int v10; // r15d
  int v11; // r12d
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  unsigned int v14; // edx
  signed int v15; // edi
  char *ResponseMimeType; // rax
  struct WSABUF_VECTORS *v17; // r9
  signed int LastError; // eax
  __int128 v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+40h] [rbp-29h]
  struct _HSE_SEND_HEADER_EX_INFO lpMem; // [rsp+48h] [rbp-21h] BYREF
  __int128 v22; // [rsp+68h] [rbp-1h]

  v4 = *((_DWORD *)this + 13);
  v6 = *((_QWORD *)this + 1);
  v20 = 0;
  LODWORD(v8) = a3;
  v19 = 0;
  result = _stricmp(*(const char **)(v6 + 104), "HEAD");
  v10 = result;
  v11 = v4 & 0x800;
  if ( v11 && !result )
    return result;
  memset(&lpMem, 0, sizeof(lpMem));
  v22 = 0;
  v12 = ALLOC_CACHE_HANDLER::Alloc(CResponseBufferSet::sm_pach);
  v13 = v12;
  if ( !v12 )
    return -2147024882;
  v12[42] &= 0xFFFFFFFC;
  *((_QWORD *)v12 + 3) = 0;
  *((_QWORD *)v12 + 19) = v12 + 6;
  *(_QWORD *)v12 = 0;
  *((_QWORD *)v12 + 1) = 0;
  *((_QWORD *)v12 + 2) = 0;
  v12[40] = 0;
  v12[41] = 16;
  v15 = CResponseBufferSet::Init((CResponseBufferSet *)v12, 0x400000u);
  if ( v15 >= 0 )
  {
    if ( !(_DWORD)v8 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
    }
    if ( !v11 )
    {
      ResponseMimeType = (char *)GetResponseMimeType(this);
      v15 = CResponse::ConstructSimpleHeaders(&lpMem, v8, ResponseMimeType, 0, 0);
      if ( v15 < 0 )
        goto LABEL_19;
      lpMem.fKeepConn = 1;
    }
    v17 = 0;
    if ( a4 )
    {
      v13[42] &= ~1u;
      *((_QWORD *)v13 + 2) = a4;
    }
    if ( !v10 )
      goto LABEL_16;
    v15 = CResponseBuffer::Write(*(CResponseBuffer **)v13, a2, v8, 0, a4 != 0);
    if ( v15 >= 0 )
    {
      CResponseVector::GetVectors((CResponseVector *)(*(_QWORD *)v13 + 8LL), (struct WSABUF_VECTORS *)&v19);
      v17 = (struct WSABUF_VECTORS *)&v19;
LABEL_16:
      if ( !(unsigned int)CIsapiReqInfo::SendClientResponse(
                            this,
                            0,
                            (struct _HSE_SEND_ENTIRE_RESPONSE_INFO *)&lpMem,
                            v17,
                            0,
                            0) )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
LABEL_19:
  if ( lpMem.pszStatus )
    HeapFree(g_hDenaliHeap, 0, (LPVOID)lpMem.pszStatus);
  if ( lpMem.pszHeader )
    HeapFree(g_hDenaliHeap, 0, (LPVOID)lpMem.pszHeader);
  CResponseBufferSet::`scalar deleting destructor'((CResponseBufferSet *)v13, v14);
  return v15;
}

```

## disassembly

```asm
0x180052ab0  mov     [rsp-8+arg_8], rdx
0x180052ab5  push    rbp
0x180052ab6  push    rbx
0x180052ab7  push    rsi
0x180052ab8  push    rdi
0x180052ab9  push    r12
0x180052abb  push    r13
0x180052abd  push    r14
0x180052abf  push    r15
0x180052ac1  lea     rbp, [rsp-1Fh]
0x180052ac6  sub     rsp, 88h
0x180052acd  mov     r12d, [rcx+34h]
0x180052ad1  lea     rdx, aHead; "HEAD"
0x180052ad8  mov     r13, rcx
0x180052adb  xorps   xmm0, xmm0
0x180052ade  mov     rcx, [rcx+8]
0x180052ae2  xor     eax, eax
0x180052ae4  mov     r14, r9
0x180052ae7  mov     [rbp+57h+var_80], rax
0x180052aeb  mov     esi, r8d
0x180052aee  movups  [rbp+57h+var_90], xmm0
0x180052af2  mov     rcx, [rcx+68h]; String1
0x180052af6  call    cs:__imp__stricmp
0x180052afc  xor     edi, edi
0x180052afe  mov     r15d, eax
0x180052b01  and     r12d, 800h
0x180052b08  jz      short loc_180052B12
0x180052b0a  test    eax, eax
0x180052b0c  jz      loc_180052C95
0x180052b12  mov     rcx, cs:?sm_pach@CResponseBufferSet@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBufferSet::sm_pach
0x180052b19  xorps   xmm0, xmm0
0x180052b1c  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x180052b20  movups  [rbp+57h+var_68], xmm0
0x180052b24  movups  [rbp+57h+var_58], xmm0
0x180052b28  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180052b2e  mov     rbx, rax
0x180052b31  test    rax, rax
0x180052b34  jz      loc_180052C90
0x180052b3a  and     dword ptr [rax+0A8h], 0FFFFFFFCh
0x180052b41  lea     rcx, [rax+18h]
0x180052b45  mov     [rcx], rdi
0x180052b48  mov     edx, 400000h; unsigned int
0x180052b4d  mov     [rax+98h], rcx
0x180052b54  mov     rcx, rax; this
0x180052b57  mov     [rax], rdi
0x180052b5a  mov     [rax+8], rdi
0x180052b5e  mov     [rax+10h], rdi
0x180052b62  mov     [rax+0A0h], edi
0x180052b68  mov     dword ptr [rax+0A4h], 10h
0x180052b72  call    ?Init@CResponseBufferSet@@QEAAJK@Z; CResponseBufferSet::Init(ulong)
0x180052b77  mov     edi, eax
0x180052b79  test    eax, eax
0x180052b7b  js      loc_180052C54
0x180052b81  test    esi, esi
0x180052b83  jnz     short loc_180052B96
0x180052b85  mov     rax, [rbp+57h+arg_8]
0x180052b89  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180052b8d  inc     rsi
0x180052b90  cmp     byte ptr [rax+rsi], 0
0x180052b94  jnz     short loc_180052B8D
0x180052b96  test    r12d, r12d
0x180052b99  jnz     short loc_180052BCE
0x180052b9b  mov     rcx, r13; this
0x180052b9e  call    ?GetResponseMimeType@@YAPEBDPEAVCIsapiReqInfo@@@Z; GetResponseMimeType(CIsapiReqInfo *)
0x180052ba3  mov     r8, rax; char *
0x180052ba6  mov     [rsp+0C0h+var_A0], 0; char *
0x180052baf  xor     r9d, r9d; char *
0x180052bb2  lea     rcx, [rbp+57h+lpMem]; struct _HSE_SEND_HEADER_EX_INFO *
0x180052bb6  mov     edx, esi; unsigned int
0x180052bb8  call    ?ConstructSimpleHeaders@CResponse@@SAJPEAU_HSE_SEND_HEADER_EX_INFO@@KPEAD11@Z; CResponse::ConstructSimpleHeaders(_HSE_SEND_HEADER_EX_INFO *,ulong,char *,char *,char *)
0x180052bbd  mov     edi, eax
0x180052bbf  test    eax, eax
0x180052bc1  js      loc_180052C54
0x180052bc7  mov     dword ptr [rbp+57h+var_68+8], 1
0x180052bce  xor     r9d, r9d; int
0x180052bd1  test    r14, r14
0x180052bd4  jz      short loc_180052BE1
0x180052bd6  and     dword ptr [rbx+0A8h], 0FFFFFFFEh
0x180052bdd  mov     [rbx+10h], r14
0x180052be1  test    r15d, r15d
0x180052be4  jz      short loc_180052C1B
0x180052be6  mov     rdx, [rbp+57h+arg_8]; char *
0x180052bea  xor     eax, eax
0x180052bec  mov     rcx, [rbx]; this
0x180052bef  test    r14, r14
0x180052bf2  mov     r8d, esi; unsigned int
0x180052bf5  setnz   al
0x180052bf8  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180052bfc  call    ?Write@CResponseBuffer@@QEAAJPEADKHH@Z; CResponseBuffer::Write(char *,ulong,int,int)
0x180052c01  mov     edi, eax
0x180052c03  test    eax, eax
0x180052c05  js      short loc_180052C54
0x180052c07  mov     rcx, [rbx]
0x180052c0a  lea     rdx, [rbp+57h+var_90]; struct WSABUF_VECTORS *
0x180052c0e  add     rcx, 8; this
0x180052c12  call    ?GetVectors@CResponseVector@@QEAAXPEAUWSABUF_VECTORS@@@Z; CResponseVector::GetVectors(WSABUF_VECTORS *)
0x180052c17  lea     r9, [rbp+57h+var_90]; struct WSABUF_VECTORS *
0x180052c1b  mov     [rsp+0C0h+var_98], 0; void *
0x180052c24  lea     r8, [rbp+57h+lpMem]; struct _HSE_SEND_ENTIRE_RESPONSE_INFO *
0x180052c28  xor     edx, edx; int
0x180052c2a  mov     [rsp+0C0h+var_A0], 0; void (*)(void *)
0x180052c33  mov     rcx, r13; this
0x180052c36  call    ?SendClientResponse@CIsapiReqInfo@@QEAAHHPEAU_HSE_SEND_ENTIRE_RESPONSE_INFO@@PEAUWSABUF_VECTORS@@P6AXPEAX@Z2@Z; CIsapiReqInfo::SendClientResponse(int,_HSE_SEND_ENTIRE_RESPONSE_INFO *,WSABUF_VECTORS *,void (*)(void *),void *)
0x180052c3b  test    eax, eax
0x180052c3d  jnz     short loc_180052C54
0x180052c3f  call    cs:__imp_GetLastError
0x180052c45  mov     edi, eax
0x180052c47  test    eax, eax
0x180052c49  jle     short loc_180052C54
0x180052c4b  movzx   edi, ax
0x180052c4e  or      edi, 80070000h
0x180052c54  mov     r8, [rbp+57h+lpMem]; lpMem
0x180052c58  test    r8, r8
0x180052c5b  jz      short loc_180052C6C
0x180052c5d  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180052c64  xor     edx, edx; dwFlags
0x180052c66  call    cs:__imp_HeapFree
0x180052c6c  mov     r8, [rbp+57h+lpMem+8]; lpMem
0x180052c70  test    r8, r8
0x180052c73  jz      short loc_180052C84
0x180052c75  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180052c7c  xor     edx, edx; dwFlags
0x180052c7e  call    cs:__imp_HeapFree
0x180052c84  mov     rcx, rbx; this
0x180052c87  call    ??_GCResponseBufferSet@@QEAAPEAXI@Z; CResponseBufferSet::`scalar deleting destructor'(uint)
0x180052c8c  mov     eax, edi
0x180052c8e  jmp     short loc_180052C95
0x180052c90  mov     eax, 8007000Eh
0x180052c95  add     rsp, 88h
0x180052c9c  pop     r15
0x180052c9e  pop     r14
0x180052ca0  pop     r13
0x180052ca2  pop     r12
0x180052ca4  pop     rdi
0x180052ca5  pop     rsi
0x180052ca6  pop     rbx
0x180052ca7  pop     rbp
0x180052ca8  retn
```
