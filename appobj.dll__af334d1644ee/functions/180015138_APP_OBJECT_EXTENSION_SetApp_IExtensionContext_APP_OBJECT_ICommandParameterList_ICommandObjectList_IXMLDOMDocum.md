# APP_OBJECT_EXTENSION::SetApp(IExtensionContext *,APP_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *,int)

- ea: `0x180015138`
- end: `0x180015343`
- name: `?SetApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVAPP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@H@Z`
- size: `523`
- prototype: `int(APP_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct APP_OBJECT *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013504`
- `0x180014690`
- `0x180015398`
- `0x180016200`

## callees

- `0x180001fb0`
- `0x1800049b0`
- `0x180015138`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x180015234`: `/path`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_EXTENSION::SetApp(
        APP_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct APP_OBJECT *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5,
        struct IXMLDOMDocument *a6,
        int a7)
{
  __int64 v9; // rdi
  APP_OBJECT_UTILS *v11; // rcx
  int v12; // ebx
  int v13; // eax
  __int16 *v14; // r8
  __int64 v15; // rdx
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 *v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+80h] [rbp-80h]
  __int16 v22; // [rsp+84h] [rbp-7Ch]
  unsigned int v23; // [rsp+88h] [rbp-78h]
  __int16 v24; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[510]; // [rsp+92h] [rbp-6Eh] BYREF

  v9 = 0;
  v17 = 0;
  v18 = 0;
  memset_0(v25, 0, sizeof(v25));
  v21 = 512;
  v20 = &v24;
  v22 = 256;
  v23 = 0;
  v24 = 0;
  if ( a2 && a3 && a4 )
  {
    v12 = (*(__int64 (__fastcall **)(struct APP_OBJECT *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v17);
    if ( v12 >= 0 )
    {
      v13 = APP_OBJECT_UTILS::PopParameter(v11, a2, a4, L"path", (struct STRU *)v19, 0, 1);
      v12 = v13;
      if ( v13 < 0 )
      {
        if ( v13 != -2147023483 )
          goto LABEL_8;
      }
      else
      {
        v14 = v20;
        if ( *v20 != 47 )
        {
          *(_QWORD *)&v18 = L"path";
          *((_QWORD *)&v18 + 1) = L"/path";
          v12 = -2147024809;
          (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            2147942487LL,
            3221226513LL,
            &v18,
            0);
          goto LABEL_8;
        }
        while ( v23 > 1 )
        {
          v15 = v23 - 1;
          if ( v14[v15] != 47 )
            break;
          STRU::SetLen((STRU *)v19, v15);
          v14 = v20;
        }
        v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *))(*(_QWORD *)a4 + 56LL))(
                a4,
                L"path");
        if ( v12 < 0 )
          goto LABEL_8;
      }
      v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct APP_OBJECT *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *, int))(*(_QWORD *)a2 + 168LL))(
              a2,
              a3,
              a4,
              a5,
              a6,
              a7);
    }
LABEL_8:
    v9 = v17;
    goto LABEL_17;
  }
  v12 = -2147024809;
LABEL_17:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v17 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180015138  mov     [rsp-8+arg_0], rbx
0x18001513d  push    rbp
0x18001513e  push    rsi
0x18001513f  push    rdi
0x180015140  push    r12
0x180015142  push    r13
0x180015144  push    r14
0x180015146  push    r15
0x180015148  lea     rbp, [rsp-1A0h]
0x180015150  sub     rsp, 2A0h
0x180015157  mov     rax, cs:__security_cookie
0x18001515e  xor     rax, rsp
0x180015161  mov     [rbp+1D0h+var_40], rax
0x180015168  mov     r12, [rbp+1D0h+arg_20]
0x18001516f  lea     rcx, [rbp+1D0h+var_23E]; void *
0x180015173  mov     r13, [rbp+1D0h+arg_28]
0x18001517a  mov     r15, r8
0x18001517d  mov     r14, rdx
0x180015180  xorps   xmm0, xmm0
0x180015183  xor     edi, edi
0x180015185  xor     edx, edx; Val
0x180015187  mov     r8d, 1FEh; Size
0x18001518d  mov     [rsp+2D0h+var_290], rdi
0x180015192  movups  [rsp+2D0h+var_288], xmm0
0x180015197  mov     rsi, r9
0x18001519a  call    memset_0
0x18001519f  lea     rax, [rbp+1D0h+var_240]
0x1800151a3  mov     [rbp+1D0h+var_250], 200h
0x1800151aa  mov     [rsp+2D0h+var_258], rax
0x1800151af  xor     eax, eax
0x1800151b1  mov     [rbp+1D0h+var_24C], 100h
0x1800151b7  mov     [rbp+1D0h+var_248], edi
0x1800151ba  mov     [rbp+1D0h+var_240], ax
0x1800151be  test    r14, r14
0x1800151c1  jz      loc_1800152EB
0x1800151c7  test    r15, r15
0x1800151ca  jz      loc_1800152EB
0x1800151d0  test    rsi, rsi
0x1800151d3  jz      loc_1800152EB
0x1800151d9  mov     rax, [r15]
0x1800151dc  lea     rdx, [rsp+2D0h+var_290]
0x1800151e1  mov     rcx, r15
0x1800151e4  mov     rax, [rax+30h]
0x1800151e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ed  mov     ebx, eax
0x1800151ef  test    eax, eax
0x1800151f1  js      short loc_180015271
0x1800151f3  mov     [rsp+2D0h+var_2A0], 1; int
0x1800151fb  lea     rax, [rsp+2D0h+var_278]
0x180015200  mov     [rsp+2D0h+var_2A8], edi; int
0x180015204  mov     r8, rsi; struct ICommandParameterList *
0x180015207  lea     rdi, aPath_1; "path"
0x18001520e  mov     [rsp+2D0h+var_2B0], rax; struct STRU *
0x180015213  mov     r9, rdi; unsigned __int16 *
0x180015216  mov     rdx, r14; struct IExtensionContext *
0x180015219  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001521e  mov     ebx, eax
0x180015220  test    eax, eax
0x180015222  js      loc_1800152B6
0x180015228  mov     r8, [rsp+2D0h+var_258]
0x18001522d  cmp     word ptr [r8], 2Fh ; '/'
0x180015232  jz      short loc_180015278
0x180015234  lea     rax, aPath_0; "/path"
0x18001523b  mov     qword ptr [rsp+2D0h+var_288], rdi
0x180015240  mov     qword ptr [rsp+2D0h+var_288+8], rax
0x180015245  lea     r9, [rsp+2D0h+var_288]
0x18001524a  mov     rax, [r14]
0x18001524d  mov     ebx, 80070057h
0x180015252  mov     r8d, 0C0000411h
0x180015258  mov     dword ptr [rsp+2D0h+var_2B0], 0
0x180015260  mov     edx, ebx
0x180015262  mov     rcx, r14
0x180015265  mov     rax, [rax+90h]
0x18001526c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015271  mov     rdi, [rsp+2D0h+var_290]
0x180015276  jmp     short loc_1800152F0
0x180015278  mov     eax, [rbp+1D0h+var_248]
0x18001527b  cmp     eax, 1
0x18001527e  jbe     short loc_18001529C
0x180015280  lea     edx, [rax-1]; unsigned int
0x180015283  cmp     word ptr [r8+rdx*2], 2Fh ; '/'
0x180015289  jnz     short loc_18001529C
0x18001528b  lea     rcx, [rsp+2D0h+var_278]; this
0x180015290  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180015295  mov     r8, [rsp+2D0h+var_258]
0x18001529a  jmp     short loc_180015278
0x18001529c  mov     rax, [rsi]
0x18001529f  mov     rdx, rdi
0x1800152a2  mov     rcx, rsi
0x1800152a5  mov     rax, [rax+38h]
0x1800152a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ae  mov     ebx, eax
0x1800152b0  test    eax, eax
0x1800152b2  js      short loc_180015271
0x1800152b4  jmp     short loc_1800152BD
0x1800152b6  cmp     eax, 80070585h
0x1800152bb  jnz     short loc_180015271
0x1800152bd  mov     rax, [r14]
0x1800152c0  mov     r9, r12
0x1800152c3  mov     ecx, [rbp+1D0h+arg_30]
0x1800152c9  mov     r8, rsi
0x1800152cc  mov     [rsp+2D0h+var_2A8], ecx
0x1800152d0  mov     rdx, r15
0x1800152d3  mov     rcx, r14
0x1800152d6  mov     [rsp+2D0h+var_2B0], r13
0x1800152db  mov     rax, [rax+0A8h]
0x1800152e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152e7  mov     ebx, eax
0x1800152e9  jmp     short loc_180015271
0x1800152eb  mov     ebx, 80070057h
0x1800152f0  test    rdi, rdi
0x1800152f3  jz      short loc_18001530D
0x1800152f5  mov     rax, [rdi]
0x1800152f8  mov     rcx, rdi
0x1800152fb  mov     rax, [rax+10h]
0x1800152ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015304  mov     [rsp+2D0h+var_290], 0
0x18001530d  lea     rcx, [rsp+2D0h+var_278]; this
0x180015312  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180015317  mov     eax, ebx
0x180015319  mov     rcx, [rbp+1D0h+var_40]
0x180015320  xor     rcx, rsp; StackCookie
0x180015323  call    __security_check_cookie
0x180015328  mov     rbx, [rsp+2D0h+arg_0]
0x180015330  add     rsp, 2A0h
0x180015337  pop     r15
0x180015339  pop     r14
0x18001533b  pop     r13
0x18001533d  pop     r12
0x18001533f  pop     rdi
0x180015340  pop     rsi
0x180015341  pop     rbp
0x180015342  retn
```
