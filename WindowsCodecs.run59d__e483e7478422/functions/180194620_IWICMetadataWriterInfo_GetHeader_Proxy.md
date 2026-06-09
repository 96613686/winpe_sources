# IWICMetadataWriterInfo_GetHeader_Proxy

- ea: `0x180194620`
- end: `0x180194743`
- name: `IWICMetadataWriterInfo_GetHeader_Proxy`
- size: `291`
- prototype: `HRESULT __stdcall(IWICMetadataWriterInfo *This, const GUID *const guidContainerFormat, UINT cbSize, WICMetadataHeader *pHeader, UINT *pcbActual)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bd9d4`
- `0x18017e438`
- `0x180194620`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180194724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180194724`
- `RPCRT4!NdrClientCall2` at `0x18019467f`
- `RPCRT4!NdrClientCall2` at `0x18019467f`

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
  Pointer = (unsigned int)NdrClientCall2(&stru_1801DFCB0, &byte_1801FC74A, This, guidContainerFormat, Size).Pointer;
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
0x180194620  mov     [rsp+arg_0], rbx
0x180194625  mov     [rsp+arg_8], rsi
0x18019462a  push    rdi
0x18019462b  sub     rsp, 50h
0x18019462f  xorps   xmm0, xmm0
0x180194632  mov     dword ptr [rsp+58h+Size], 0
0x18019463a  xor     eax, eax
0x18019463c  mov     rdi, r9
0x18019463f  mov     esi, r8d
0x180194642  movups  xmmword ptr [rsp+58h+Size+4], xmm0
0x180194647  movups  xmmword ptr [rsp+58h+Src], xmm0
0x18019464c  test    rcx, rcx
0x18019464f  jnz     short loc_180194661
0x180194651  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180194657  mov     ebx, 80070057h
0x18019465c  jmp     loc_180194716
0x180194661  lea     rax, [rsp+58h+Size]
0x180194666  mov     r9, rdx
0x180194669  mov     r8, rcx
0x18019466c  mov     [rsp+58h+var_38], rax
0x180194671  lea     rdx, byte_1801FC74A; pFormat
0x180194678  lea     rcx, stru_1801DFCB0; pStubDescriptor
0x18019467f  call    cs:__imp_NdrClientCall2
0x180194686  nop     dword ptr [rax+rax+00h]
0x18019468b  mov     rbx, rax
0x18019468e  test    eax, eax
0x180194690  jns     short loc_1801946A3
0x180194692  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180194699  jz      loc_18019471F
0x18019469f  mov     ecx, eax
0x1801946a1  jmp     short loc_18019471A
0x1801946a3  mov     edx, dword ptr [rsp+58h+Size+8]
0x1801946a7  lea     eax, [rdx+20h]
0x1801946aa  cmp     eax, edx
0x1801946ac  jb      short loc_18019470A
0x1801946ae  mov     rcx, [rsp+58h+pcbActual]
0x1801946b6  xor     ebx, ebx
0x1801946b8  test    rcx, rcx
0x1801946bb  jz      short loc_1801946BF
0x1801946bd  mov     [rcx], eax
0x1801946bf  test    rdi, rdi
0x1801946c2  jz      short loc_18019471F
0x1801946c4  cmp     esi, eax
0x1801946c6  jnb     short loc_1801946CF
0x1801946c8  mov     ebx, 88982F8Ch
0x1801946cd  jmp     short loc_18019470F
0x1801946cf  movups  xmm1, xmmword ptr [rsp+58h+Src]
0x1801946d4  movups  xmm0, xmmword ptr [rsp+58h+Size]
0x1801946d9  movq    rax, xmm1
0x1801946de  mov     [rsp+58h+Src], rax
0x1801946e3  movups  xmmword ptr [rdi], xmm0
0x1801946e6  movups  xmmword ptr [rdi+10h], xmm1
0x1801946ea  test    rax, rax
0x1801946ed  jz      short loc_180194704
0x1801946ef  lea     rcx, [rdi+20h]; void *
0x1801946f3  mov     r8, rdx; Size
0x1801946f6  mov     rdx, rax; Src
0x1801946f9  mov     [rdi+10h], rcx
0x1801946fd  call    memcpy_0
0x180194702  jmp     short loc_18019471F
0x180194704  mov     dword ptr [rsp+58h+Size+8], ebx
0x180194708  jmp     short loc_18019471F
0x18019470a  mov     ebx, 80070216h
0x18019470f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180194716  jz      short loc_18019471F
0x180194718  mov     ecx, ebx; int
0x18019471a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18019471f  mov     rcx, [rsp+58h+Src]; pv
0x180194724  call    cs:__imp_CoTaskMemFree
0x18019472b  nop     dword ptr [rax+rax+00h]
0x180194730  mov     rsi, [rsp+58h+arg_8]
0x180194735  mov     eax, ebx
0x180194737  mov     rbx, [rsp+58h+arg_0]
0x18019473c  add     rsp, 50h
0x180194740  pop     rdi
0x180194741  retn
```
