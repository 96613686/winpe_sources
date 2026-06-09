# SetErrorInfoHelper(long,_GUID const &,_GUID const &)

- ea: `0x180081f68`
- end: `0x1800820e9`
- name: `?SetErrorInfoHelper@@YAXJAEBU_GUID@@0@Z`
- size: `385`
- prototype: `void __fastcall(DWORD dwMessageId, const struct _GUID *, const struct _GUID *)`
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x180031170`
- `0x180031264`
- `0x1800315f0`
- `0x1800316f0`
- `0x1800331dc`
- `0x180036898`
- `0x18003b820`
- `0x18003bd60`
- `0x18003c450`
- `0x18003c8a0`
- `0x18003d8f0`
- `0x180041120`
- `0x180041680`
- `0x180041eb0`
- `0x180044a80`
- `0x180044f00`
- `0x180045060`
- `0x180045350`
- `0x180045c00`
- `0x180045f60`

## callees

- `0x18000a0f0`
- `0x18000f810`
- `0x180081e7c`
- `0x180081f68`
- `0x180094010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180081f9c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180081f9c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800820bd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800820bd`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180081fcf`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180081fcf`

## pseudocode

```c
void __fastcall SetErrorInfoHelper(signed int dwMessageId, const struct _GUID *a2, ICreateErrorInfo *a3)
{
  IErrorInfo *v5; // rdx
  DWORD v6; // edi
  _WORD *v7; // rsi
  int v8; // ebx
  int ErrorDescriptionForHR; // eax
  ICreateErrorInfo *v10; // [rsp+60h] [rbp+40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+68h] [rbp+48h] BYREF

  if ( dwMessageId < 0 )
  {
    v10 = a3;
    pperrinfo = 0;
    if ( GetErrorInfo(0, &pperrinfo) >= 0 )
    {
      v5 = pperrinfo;
      if ( !pperrinfo )
      {
        if ( (unsigned int)(dwMessageId + 2147217408) <= 0x2A )
        {
          v10 = (ICreateErrorInfo *)pperrinfo;
          if ( CreateErrorInfo(&v10) < 0 )
            goto LABEL_21;
          v6 = 260;
          v7 = 0;
          while ( 1 )
          {
            v8 = -2147024882;
            SeFree(v7);
            v7 = SeAlloc(saturated_mul(v6, 2u));
            if ( !v7 )
              break;
            *v7 = 0;
            ErrorDescriptionForHR = CreateErrorDescriptionForHR(dwMessageId, v7, v6);
            v8 = ErrorDescriptionForHR;
            if ( ErrorDescriptionForHR != -2147024662 )
            {
              if ( ErrorDescriptionForHR >= 0 )
                v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _WORD *))v10->lpVtbl->SetDescription)(v10, v7);
              break;
            }
            if ( 2 * v6 <= v6 )
            {
              v8 = -2147217379;
              break;
            }
            v6 *= 2;
          }
          SeFree(v7);
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))v10->lpVtbl->SetGUID)(v10, a2);
            if ( v8 >= 0 )
              v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v10->lpVtbl->QueryInterface)(
                     v10,
                     &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
                     &pperrinfo);
          }
          ((void (__fastcall *)(ICreateErrorInfo *))v10->lpVtbl->Release)(v10);
          if ( v8 < 0 )
            goto LABEL_21;
          v5 = pperrinfo;
        }
        if ( !v5 )
          return;
      }
      SetErrorInfo(0, v5);
    }
LABEL_21:
    if ( pperrinfo )
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x180081f68  test    ecx, ecx
0x180081f6a  jns     locret_1800820E8
0x180081f70  mov     [rsp-28h+arg_0], rbx
0x180081f75  mov     [rsp-28h+arg_10], r8
0x180081f7a  push    rbp
0x180081f7b  push    rsi
0x180081f7c  push    rdi
0x180081f7d  push    r14
0x180081f7f  push    r15
0x180081f81  mov     rbp, rsp
0x180081f84  sub     rsp, 20h
0x180081f88  mov     r15, rdx
0x180081f8b  mov     [rbp+pperrinfo], 0
0x180081f93  mov     r14d, ecx
0x180081f96  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180081f9a  xor     ecx, ecx; dwReserved
0x180081f9c  call    cs:__imp_GetErrorInfo
0x180081fa2  test    eax, eax
0x180081fa4  js      loc_1800820C3
0x180081faa  mov     rdx, [rbp+pperrinfo]
0x180081fae  test    rdx, rdx
0x180081fb1  jnz     loc_1800820BB
0x180081fb7  lea     eax, [r14+7FFBF000h]
0x180081fbe  cmp     eax, 2Ah ; '*'
0x180081fc1  ja      loc_1800820B6
0x180081fc7  lea     rcx, [rbp+arg_10]; pperrinfo
0x180081fcb  mov     [rbp+arg_10], rdx
0x180081fcf  call    cs:__imp_CreateErrorInfo
0x180081fd5  test    eax, eax
0x180081fd7  js      loc_1800820C3
0x180081fdd  mov     edi, 104h
0x180081fe2  xor     esi, esi
0x180081fe4  mov     rcx, rsi; void *
0x180081fe7  mov     ebx, 8007000Eh
0x180081fec  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180081ff1  mov     ecx, edi
0x180081ff3  mov     eax, 2
0x180081ff8  mul     rcx
0x180081ffb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180082002  cmovb   rax, rcx
0x180082006  mov     rcx, rax; unsigned __int64
0x180082009  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18008200e  mov     rsi, rax
0x180082011  test    rax, rax
0x180082014  jz      short loc_18008205D
0x180082016  xor     eax, eax
0x180082018  mov     r8d, edi; nSize
0x18008201b  mov     rdx, rsi; lpBuffer
0x18008201e  mov     [rsi], ax
0x180082021  mov     ecx, r14d; dwMessageId
0x180082024  call    ?CreateErrorDescriptionForHR@@YAJJPEAGK@Z; CreateErrorDescriptionForHR(long,ushort *,ulong)
0x180082029  mov     ebx, eax
0x18008202b  cmp     eax, 800700EAh
0x180082030  jnz     short loc_180082044
0x180082032  lea     eax, [rdi+rdi]
0x180082035  cmp     eax, edi
0x180082037  jbe     short loc_18008203D
0x180082039  mov     edi, eax
0x18008203b  jmp     short loc_180081FE4
0x18008203d  mov     ebx, 8004101Dh
0x180082042  jmp     short loc_18008205D
0x180082044  test    eax, eax
0x180082046  js      short loc_18008205D
0x180082048  mov     rcx, [rbp+arg_10]
0x18008204c  mov     rdx, rsi
0x18008204f  mov     rax, [rcx]
0x180082052  mov     rax, [rax+28h]
0x180082056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008205b  mov     ebx, eax
0x18008205d  mov     rcx, rsi; void *
0x180082060  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180082065  test    ebx, ebx
0x180082067  js      short loc_18008209E
0x180082069  mov     rcx, [rbp+arg_10]
0x18008206d  mov     rdx, r15
0x180082070  mov     rax, [rcx]
0x180082073  mov     rax, [rax+18h]
0x180082077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008207c  mov     ebx, eax
0x18008207e  test    eax, eax
0x180082080  js      short loc_18008209E
0x180082082  mov     rcx, [rbp+arg_10]
0x180082086  lea     r8, [rbp+pperrinfo]
0x18008208a  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x180082091  mov     rax, [rcx]
0x180082094  mov     rax, [rax]
0x180082097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008209c  mov     ebx, eax
0x18008209e  mov     rcx, [rbp+arg_10]
0x1800820a2  mov     rax, [rcx]
0x1800820a5  mov     rax, [rax+10h]
0x1800820a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800820ae  test    ebx, ebx
0x1800820b0  js      short loc_1800820C3
0x1800820b2  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800820b6  test    rdx, rdx
0x1800820b9  jz      short loc_1800820D8
0x1800820bb  xor     ecx, ecx; dwReserved
0x1800820bd  call    cs:__imp_SetErrorInfo
0x1800820c3  mov     rcx, [rbp+pperrinfo]
0x1800820c7  test    rcx, rcx
0x1800820ca  jz      short loc_1800820D8
0x1800820cc  mov     rax, [rcx]
0x1800820cf  mov     rax, [rax+10h]
0x1800820d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800820d8  mov     rbx, [rsp+20h+arg_0]
0x1800820dd  add     rsp, 20h
0x1800820e1  pop     r15
0x1800820e3  pop     r14
0x1800820e5  pop     rdi
0x1800820e6  pop     rsi
0x1800820e7  pop     rbp
0x1800820e8  retn
```
