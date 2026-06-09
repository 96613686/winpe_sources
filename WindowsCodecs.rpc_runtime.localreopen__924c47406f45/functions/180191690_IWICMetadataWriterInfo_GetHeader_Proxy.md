# IWICMetadataWriterInfo_GetHeader_Proxy

- ea: `0x180191690`
- end: `0x1801917a6`
- name: `IWICMetadataWriterInfo_GetHeader_Proxy`
- size: `278`
- prototype: `HRESULT __stdcall(IWICMetadataWriterInfo *This, const GUID *const guidContainerFormat, UINT cbSize, WICMetadataHeader *pHeader, UINT *pcbActual)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bb784`
- `0x18017b528`
- `0x180191690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019178e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019178e`
- `RPCRT4!NdrClientCall2` at `0x1801916ef`
- `RPCRT4!NdrClientCall2` at `0x1801916ef`

## pseudocode

```c
HRESULT __stdcall IWICMetadataWriterInfo_GetHeader_Proxy(
        IWICMetadataWriterInfo *This,
        const GUID *const guidContainerFormat,
        UINT cbSize,
        WICMetadataHeader *pHeader,
        UINT *pcbActual)
{
  bool v7; // zf
  HRESULT v8; // ebx
  int Pointer; // eax
  int v10; // ecx
  size_t v11; // rdx
  UINT v12; // eax
  __int128 v13; // xmm1
  const void *v14; // rax
  size_t Size[5]; // [rsp+30h] [rbp-28h] BYREF

  memset(Size, 0, 32);
  if ( !This )
  {
    v7 = (_DWORD)g_doStackCaptures == 0;
    v8 = -2147024809;
LABEL_17:
    if ( !v7 )
    {
      v10 = v8;
      goto LABEL_19;
    }
    goto LABEL_20;
  }
  Pointer = (unsigned int)NdrClientCall2(&stru_1801DBCC0, &byte_1801F87DA, This, guidContainerFormat, Size).Pointer;
  v8 = Pointer;
  if ( Pointer >= 0 )
  {
    v11 = LODWORD(Size[1]);
    v12 = LODWORD(Size[1]) + 32;
    if ( (unsigned int)(LODWORD(Size[1]) + 32) < LODWORD(Size[1]) )
    {
      v8 = -2147024362;
    }
    else
    {
      v8 = 0;
      if ( pcbActual )
        *pcbActual = v12;
      if ( !pHeader )
        goto LABEL_20;
      if ( cbSize >= v12 )
      {
        v13 = *(_OWORD *)&Size[2];
        v14 = (const void *)Size[2];
        *(_OWORD *)&pHeader->Position.LowPart = *(_OWORD *)Size;
        *(_OWORD *)&pHeader->Header = v13;
        if ( v14 )
        {
          pHeader->Header = (BYTE *)&pHeader[1];
          memcpy_0(&pHeader[1], v14, v11);
        }
        else
        {
          LODWORD(Size[1]) = 0;
        }
        goto LABEL_20;
      }
      v8 = -2003292276;
    }
    v7 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_17;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
    v10 = Pointer;
LABEL_19:
    DoStackCapture(v10);
  }
LABEL_20:
  CoTaskMemFree((LPVOID)Size[2]);
  return v8;
}

```

## disassembly

```asm
0x180191690  mov     [rsp+arg_0], rbx
0x180191695  mov     [rsp+arg_8], rsi
0x18019169a  push    rdi
0x18019169b  sub     rsp, 50h
0x18019169f  xorps   xmm0, xmm0
0x1801916a2  mov     dword ptr [rsp+58h+Size], 0
0x1801916aa  xor     eax, eax
0x1801916ac  mov     rdi, r9
0x1801916af  mov     esi, r8d
0x1801916b2  movups  xmmword ptr [rsp+58h+Size+4], xmm0
0x1801916b7  movups  xmmword ptr [rsp+58h+Src], xmm0
0x1801916bc  test    rcx, rcx
0x1801916bf  jnz     short loc_1801916D1
0x1801916c1  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801916c7  mov     ebx, 80070057h
0x1801916cc  jmp     loc_180191780
0x1801916d1  lea     rax, [rsp+58h+Size]
0x1801916d6  mov     r9, rdx
0x1801916d9  mov     r8, rcx
0x1801916dc  mov     [rsp+58h+var_38], rax
0x1801916e1  lea     rdx, byte_1801F87DA; pFormat
0x1801916e8  lea     rcx, stru_1801DBCC0; pStubDescriptor
0x1801916ef  call    cs:__imp_NdrClientCall2
0x1801916f5  mov     rbx, rax
0x1801916f8  test    eax, eax
0x1801916fa  jns     short loc_18019170D
0x1801916fc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180191703  jz      loc_180191789
0x180191709  mov     ecx, eax
0x18019170b  jmp     short loc_180191784
0x18019170d  mov     edx, dword ptr [rsp+58h+Size+8]
0x180191711  lea     eax, [rdx+20h]
0x180191714  cmp     eax, edx
0x180191716  jb      short loc_180191774
0x180191718  mov     rcx, [rsp+58h+pcbActual]
0x180191720  xor     ebx, ebx
0x180191722  test    rcx, rcx
0x180191725  jz      short loc_180191729
0x180191727  mov     [rcx], eax
0x180191729  test    rdi, rdi
0x18019172c  jz      short loc_180191789
0x18019172e  cmp     esi, eax
0x180191730  jnb     short loc_180191739
0x180191732  mov     ebx, 88982F8Ch
0x180191737  jmp     short loc_180191779
0x180191739  movups  xmm1, xmmword ptr [rsp+58h+Src]
0x18019173e  movups  xmm0, xmmword ptr [rsp+58h+Size]
0x180191743  movq    rax, xmm1
0x180191748  mov     [rsp+58h+Src], rax
0x18019174d  movups  xmmword ptr [rdi], xmm0
0x180191750  movups  xmmword ptr [rdi+10h], xmm1
0x180191754  test    rax, rax
0x180191757  jz      short loc_18019176E
0x180191759  lea     rcx, [rdi+20h]; void *
0x18019175d  mov     r8, rdx; Size
0x180191760  mov     rdx, rax; Src
0x180191763  mov     [rdi+10h], rcx
0x180191767  call    memcpy_0
0x18019176c  jmp     short loc_180191789
0x18019176e  mov     dword ptr [rsp+58h+Size+8], ebx
0x180191772  jmp     short loc_180191789
0x180191774  mov     ebx, 80070216h
0x180191779  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180191780  jz      short loc_180191789
0x180191782  mov     ecx, ebx; int
0x180191784  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180191789  mov     rcx, [rsp+58h+Src]; pv
0x18019178e  call    cs:__imp_CoTaskMemFree
0x180191794  mov     rsi, [rsp+58h+arg_8]
0x180191799  mov     eax, ebx
0x18019179b  mov     rbx, [rsp+58h+arg_0]
0x1801917a0  add     rsp, 50h
0x1801917a4  pop     rdi
0x1801917a5  retn
```
