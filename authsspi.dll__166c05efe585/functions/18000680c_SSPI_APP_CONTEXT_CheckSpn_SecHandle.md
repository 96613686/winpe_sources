# SSPI_APP_CONTEXT::CheckSpn(_SecHandle *)

- ea: `0x18000680c`
- end: `0x1800068ba`
- name: `?CheckSpn@SSPI_APP_CONTEXT@@QEAAJPEAU_SecHandle@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(SSPI_APP_CONTEXT *this, struct _SecHandle *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x18000680c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006883`
- `msvcrt!_wcsicmp` at `0x180006883`
- `SspiCli!FreeContextBuffer` at `0x1800068a3`
- `SspiCli!FreeContextBuffer` at `0x1800068a3`
- `SspiCli!QueryContextAttributesW` at `0x180006848`
- `SspiCli!QueryContextAttributesW` at `0x180006848`

## pseudocode

```c
__int64 __fastcall SSPI_APP_CONTEXT::CheckSpn(SSPI_APP_CONTEXT *this, struct _SecHandle *a2)
{
  bool v2; // zf
  unsigned int v4; // ebx
  SECURITY_STATUS v5; // eax
  __int64 v6; // rbx
  wchar_t *pBuffer; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 20) == 0;
  pBuffer = 0;
  if ( v2 || (*((_BYTE *)this + 84) & 1) == 0 || (*((_BYTE *)this + 84) & 2) != 0 )
  {
    return 0;
  }
  else
  {
    v5 = QueryContextAttributesW(a2, 0x1Bu, &pBuffer);
    v4 = v5;
    if ( v5 == -2146893053 )
    {
      v4 = 0;
      if ( *((_DWORD *)this + 20) == 2 )
        v4 = -2146893018;
    }
    else if ( v5 >= 0 )
    {
      v6 = 0;
      if ( *((_DWORD *)this + 24) )
      {
        while ( _wcsicmp(*(const wchar_t **)(*(_QWORD *)(*((_QWORD *)this + 11) + 8 * v6) + 8LL), pBuffer) )
        {
          v6 = (unsigned int)(v6 + 1);
          if ( (unsigned int)v6 >= *((_DWORD *)this + 24) )
            goto LABEL_13;
        }
        v4 = 0;
      }
      else
      {
LABEL_13:
        v4 = -2146893018;
      }
    }
    if ( pBuffer )
      FreeContextBuffer(pBuffer);
  }
  return v4;
}

```

## disassembly

```asm
0x18000680c  mov     [rsp+arg_8], rbx
0x180006811  push    rdi
0x180006812  sub     rsp, 20h
0x180006816  cmp     dword ptr [rcx+50h], 0
0x18000681a  mov     rax, rdx
0x18000681d  mov     rdi, rcx
0x180006820  mov     [rsp+28h+pBuffer], 0
0x180006829  jnz     short loc_18000682F
0x18000682b  xor     ebx, ebx
0x18000682d  jmp     short loc_1800068A9
0x18000682f  test    byte ptr [rcx+54h], 1
0x180006833  jz      short loc_18000682B
0x180006835  test    byte ptr [rcx+54h], 2
0x180006839  jnz     short loc_18000682B
0x18000683b  lea     r8, [rsp+28h+pBuffer]; pBuffer
0x180006840  mov     edx, 1Bh; ulAttribute
0x180006845  mov     rcx, rax; phContext
0x180006848  call    cs:__imp_QueryContextAttributesW
0x18000684e  mov     ebx, eax
0x180006850  cmp     eax, 80090303h
0x180006855  jnz     short loc_180006867
0x180006857  xor     ebx, ebx
0x180006859  mov     eax, 80090326h
0x18000685e  cmp     dword ptr [rdi+50h], 2
0x180006862  cmovz   ebx, eax
0x180006865  jmp     short loc_180006899
0x180006867  test    eax, eax
0x180006869  js      short loc_180006899
0x18000686b  xor     ebx, ebx
0x18000686d  cmp     [rdi+60h], ebx
0x180006870  jbe     short loc_180006894
0x180006872  mov     rax, [rdi+58h]
0x180006876  mov     rdx, [rsp+28h+pBuffer]; String2
0x18000687b  mov     rcx, [rax+rbx*8]
0x18000687f  mov     rcx, [rcx+8]; String1
0x180006883  call    cs:__imp__wcsicmp
0x180006889  test    eax, eax
0x18000688b  jz      short loc_1800068B6
0x18000688d  inc     ebx
0x18000688f  cmp     ebx, [rdi+60h]
0x180006892  jb      short loc_180006872
0x180006894  mov     ebx, 80090326h
0x180006899  mov     rcx, [rsp+28h+pBuffer]; pvContextBuffer
0x18000689e  test    rcx, rcx
0x1800068a1  jz      short loc_1800068A9
0x1800068a3  call    cs:__imp_FreeContextBuffer
0x1800068a9  mov     eax, ebx
0x1800068ab  mov     rbx, [rsp+28h+arg_8]
0x1800068b0  add     rsp, 20h
0x1800068b4  pop     rdi
0x1800068b5  retn
0x1800068b6  xor     ebx, ebx
0x1800068b8  jmp     short loc_180006899
```
