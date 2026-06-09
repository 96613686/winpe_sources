# SensorStream::AddInternalAttributes(void)

- ea: `0x180026eb0`
- end: `0x1800270a8`
- name: `?AddInternalAttributes@SensorStream@@UEAAJXZ`
- size: `504`
- prototype: `__int64 __fastcall(struct IMFAttributes *this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005fa0`
- `0x180026eb0`
- `0x18002715c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ec3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ec3`
- `MFPlat!MFCreateCollection` at `0x180026f24`
- `MFPlat!MFCreateCollection` at `0x180026f24`

## pseudocode

```c
__int64 __fastcall SensorStream::AddInternalAttributes(struct IMFAttributes *this)
{
  struct IMFAttributesVtbl *lpVtbl; // rcx
  struct IMFCollection *v3; // rcx
  int v4; // eax
  unsigned int v5; // edi
  __int64 i; // rbp
  __int64 j; // rbp
  __int64 v9; // rdx
  int v10; // [rsp+50h] [rbp+8h] BYREF
  struct IMFCollection *v11; // [rsp+58h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)&this[2]);
  lpVtbl = this[8].lpVtbl;
  v11 = 0;
  v10 = 0;
  if ( (*((int (__fastcall **)(struct IMFAttributesVtbl *, __int64 *, int *))lpVtbl->QueryInterface + 14))(
         lpVtbl,
         MF_SENSORSTREAM_SENSORMEDIATYPEINFO_LIST,
         &v10) < 0
    || (v5 = 0,
        (*((int (__fastcall **)(struct IMFAttributesVtbl *, __int64 *, int *))this[8].lpVtbl->QueryInterface + 14))(
          this[8].lpVtbl,
          MF_SENSORSTREAM_SENSORMEDIATYPEENTRY_LIST,
          &v10) < 0) )
  {
    if ( LODWORD(this[10].lpVtbl) || LODWORD(this[13].lpVtbl) )
    {
      v3 = v11;
      v11 = 0;
      if ( v3 )
        ((void (__fastcall *)(struct IMFCollection *))v3->lpVtbl->Release)(v3);
      v4 = MFCreateCollection(&v11);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_13;
        v9 = 104;
      }
      else
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= LODWORD(this[10].lpVtbl) )
          {
            for ( j = 0; (unsigned int)j < LODWORD(this[13].lpVtbl); j = (unsigned int)(j + 1) )
            {
              v4 = ((__int64 (__fastcall *)(struct IMFCollection *, _QWORD))v11->lpVtbl->AddElement)(
                     v11,
                     *((_QWORD *)&this[12].lpVtbl->QueryInterface + j));
              v5 = v4;
              if ( v4 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_13;
                v9 = 106;
                goto LABEL_31;
              }
            }
            v4 = FSAddSensorStreamAttributes(this, v11);
            v5 = v4;
            if ( v4 < 0 && g_wppLevels )
            {
              v9 = 107;
              goto LABEL_31;
            }
            goto LABEL_13;
          }
          v4 = ((__int64 (__fastcall *)(struct IMFCollection *, _QWORD))v11->lpVtbl->AddElement)(
                 v11,
                 *((_QWORD *)&this[9].lpVtbl->QueryInterface + i));
          v5 = v4;
          if ( v4 < 0 )
            break;
        }
        if ( !g_wppLevels )
          goto LABEL_13;
        v9 = 105;
      }
LABEL_31:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, this, v4);
    }
    else
    {
      v5 = -1072875850;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
          this,
          -1072875850);
    }
  }
LABEL_13:
  if ( v11 )
    ((void (__fastcall *)(struct IMFCollection *))v11->lpVtbl->Release)(v11);
  LeaveCriticalSection((LPCRITICAL_SECTION)&this[2]);
  return v5;
}

```

## disassembly

```asm
0x180026eb0  mov     [rsp+arg_10], rbx
0x180026eb5  push    rbp
0x180026eb6  push    rsi
0x180026eb7  push    rdi
0x180026eb8  sub     rsp, 30h
0x180026ebc  mov     rsi, rcx
0x180026ebf  add     rcx, 10h; lpCriticalSection
0x180026ec3  call    cs:__imp_EnterCriticalSection
0x180026ec9  mov     rcx, [rsi+40h]
0x180026ecd  lea     r8, [rsp+48h+arg_0]
0x180026ed2  mov     [rsp+48h+arg_8], 0
0x180026edb  lea     rdx, MF_SENSORSTREAM_SENSORMEDIATYPEINFO_LIST
0x180026ee2  mov     [rsp+48h+arg_0], 0
0x180026eea  mov     rax, [rcx]
0x180026eed  mov     rax, [rax+70h]
0x180026ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ef6  test    eax, eax
0x180026ef8  jns     loc_180026FB3
0x180026efe  cmp     dword ptr [rsi+50h], 0
0x180026f02  jz      loc_180026FDA
0x180026f08  mov     rcx, [rsp+48h+arg_8]
0x180026f0d  mov     [rsp+48h+arg_8], 0
0x180026f16  test    rcx, rcx
0x180026f19  jnz     loc_180027000
0x180026f1f  lea     rcx, [rsp+48h+arg_8]
0x180026f24  call    cs:__imp_MFCreateCollection
0x180026f2a  mov     edi, eax
0x180026f2c  test    eax, eax
0x180026f2e  js      loc_180027011
0x180026f34  xor     ebp, ebp
0x180026f36  cmp     ebp, [rsi+50h]
0x180026f39  jnb     short loc_180026F62
0x180026f3b  mov     rcx, [rsp+48h+arg_8]
0x180026f40  mov     rdx, [rsi+48h]
0x180026f44  mov     rax, [rcx]
0x180026f47  mov     rdx, [rdx+rbp*8]
0x180026f4b  mov     rax, [rax+28h]
0x180026f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f54  mov     edi, eax
0x180026f56  test    eax, eax
0x180026f58  js      loc_180027025
0x180026f5e  inc     ebp
0x180026f60  jmp     short loc_180026F36
0x180026f62  xor     ebp, ebp
0x180026f64  cmp     ebp, [rsi+68h]
0x180026f67  jb      loc_180027039
0x180026f6d  mov     rdx, [rsp+48h+arg_8]; struct IMFCollection *
0x180026f72  mov     rcx, rsi; struct IMFAttributes *
0x180026f75  call    ?FSAddSensorStreamAttributes@@YAJPEAUIMFAttributes@@PEAUIMFCollection@@@Z; FSAddSensorStreamAttributes(IMFAttributes *,IMFCollection *)
0x180026f7a  mov     edi, eax
0x180026f7c  test    eax, eax
0x180026f7e  js      loc_180027073
0x180026f84  mov     rcx, [rsp+48h+arg_8]
0x180026f89  test    rcx, rcx
0x180026f8c  jz      short loc_180026F9A
0x180026f8e  mov     rax, [rcx]
0x180026f91  mov     rax, [rax+10h]
0x180026f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f9a  lea     rcx, [rsi+10h]; lpCriticalSection
0x180026f9e  call    cs:__imp_LeaveCriticalSection
0x180026fa4  mov     rbx, [rsp+48h+arg_10]
0x180026fa9  mov     eax, edi
0x180026fab  add     rsp, 30h
0x180026faf  pop     rdi
0x180026fb0  pop     rsi
0x180026fb1  pop     rbp
0x180026fb2  retn
0x180026fb3  mov     rcx, [rsi+40h]
0x180026fb7  lea     r8, [rsp+48h+arg_0]
0x180026fbc  lea     rdx, MF_SENSORSTREAM_SENSORMEDIATYPEENTRY_LIST
0x180026fc3  xor     edi, edi
0x180026fc5  mov     rax, [rcx]
0x180026fc8  mov     rax, [rax+70h]
0x180026fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fd1  test    eax, eax
0x180026fd3  jns     short loc_180026F84
0x180026fd5  jmp     loc_180026EFE
0x180026fda  cmp     dword ptr [rsi+68h], 0
0x180026fde  jnz     loc_180026F08
0x180026fe4  mov     edi, 0C00D36B6h
0x180026fe9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026ff0  jb      short loc_180026F84
0x180026ff2  mov     edx, 67h ; 'g'
0x180026ff7  mov     [rsp+48h+var_28], edi
0x180026ffb  jmp     loc_180027089
0x180027000  mov     rax, [rcx]
0x180027003  mov     rax, [rax+10h]
0x180027007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002700c  jmp     loc_180026F1F
0x180027011  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027018  jb      loc_180026F84
0x18002701e  mov     edx, 68h ; 'h'
0x180027023  jmp     short loc_180027085
0x180027025  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002702c  jb      loc_180026F84
0x180027032  mov     edx, 69h ; 'i'
0x180027037  jmp     short loc_180027085
0x180027039  mov     rcx, [rsp+48h+arg_8]
0x18002703e  mov     rdx, [rsi+60h]
0x180027042  mov     rax, [rcx]
0x180027045  mov     rdx, [rdx+rbp*8]
0x180027049  mov     rax, [rax+28h]
0x18002704d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027052  mov     edi, eax
0x180027054  test    eax, eax
0x180027056  js      short loc_18002705F
0x180027058  inc     ebp
0x18002705a  jmp     loc_180026F64
0x18002705f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027066  jb      loc_180026F84
0x18002706c  mov     edx, 6Ah ; 'j'
0x180027071  jmp     short loc_180027085
0x180027073  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002707a  jb      loc_180026F84
0x180027080  mov     edx, 6Bh ; 'k'
0x180027085  mov     [rsp+48h+var_28], eax
0x180027089  mov     rcx, cs:WPP_GLOBAL_Control
0x180027090  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x180027097  mov     r9, rsi
0x18002709a  mov     rcx, [rcx+10h]
0x18002709e  call    WPP_SF_qD
0x1800270a3  jmp     loc_180026F84
```
