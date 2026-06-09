# AxISEvents::DebugMsg(ulong,uchar,ushort *,...)

- ea: `0x18000725c`
- end: `0x1800072ec`
- name: `?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ`
- size: `144`
- prototype: `void(AxISEvents *__hidden this, unsigned int, unsigned __int8, unsigned __int16 *, ...)`
- caller_count: `29`
- callee_count: `4`
- tags: ``

## callers

- `0x180002e78`
- `0x180003260`
- `0x1800038dc`
- `0x180003afc`
- `0x18000401c`
- `0x180005ee0`
- `0x180006370`
- `0x180006518`
- `0x180006640`
- `0x180006aec`
- `0x180006e30`
- `0x180006ea0`
- `0x18000a2fc`
- `0x18000a9a0`
- `0x18000aa50`
- `0x18000ab24`
- `0x18000bbfc`
- `0x18000bf6c`
- `0x18000c224`
- `0x18000d914`
- `0x18000f170`
- `0x180010e80`
- `0x180012244`
- `0x180012408`
- `0x1800128e4`
- `0x180012c24`
- `0x1800131a4`
- `0x180013330`
- `0x180013460`

## callees

- `0x180001720`
- `0x18000725c`
- `0x1800073c0`
- `0x18000743c`

## pseudocode

```c
void AxISEvents::DebugMsg(AxISEvents *this, unsigned int a2, unsigned __int8 a3, unsigned __int16 *a4, ...)
{
  unsigned __int16 v7[1024]; // [rsp+30h] [rbp-828h] BYREF
  va_list va; // [rsp+880h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( *((_DWORD *)this + 3)
    && (a2 & *((_QWORD *)this + 2)) != 0
    && a3 <= *((_BYTE *)this + 24)
    && (int)StringCchVPrintfW(v7, 0x400u, a4, va) >= 0 )
  {
    AxISEvents::TraceDebugEvent(this, a2, a3, v7);
  }
}

```

## disassembly

```asm
0x18000725c  mov     r11, rsp
0x18000725f  mov     [r11+20h], r9
0x180007263  push    rbx
0x180007264  push    rsi
0x180007265  push    rdi
0x180007266  sub     rsp, 840h
0x18000726d  mov     rax, cs:__security_cookie
0x180007274  xor     rax, rsp
0x180007277  mov     [rsp+858h+var_28], rax
0x18000727f  cmp     dword ptr [rcx+0Ch], 0
0x180007283  mov     r10, r9
0x180007286  mov     dil, r8b
0x180007289  mov     esi, edx
0x18000728b  mov     rbx, rcx
0x18000728e  mov     [rsp+858h+var_838], 0
0x180007297  jz      short loc_1800072D1
0x180007299  test    [rcx+10h], rsi
0x18000729d  jz      short loc_1800072D1
0x18000729f  cmp     r8b, [rcx+18h]
0x1800072a3  ja      short loc_1800072D1
0x1800072a5  lea     r9, [r11+28h]; char *
0x1800072a9  mov     r8, r10; unsigned __int16 *
0x1800072ac  mov     edx, 400h; unsigned __int64
0x1800072b1  lea     rcx, [rsp+858h+var_828]; unsigned __int16 *
0x1800072b6  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x1800072bb  test    eax, eax
0x1800072bd  js      short loc_1800072D1
0x1800072bf  lea     r9, [rsp+858h+var_828]; unsigned __int16 *
0x1800072c4  mov     r8b, dil; unsigned __int8
0x1800072c7  mov     edx, esi; unsigned int
0x1800072c9  mov     rcx, rbx; this
0x1800072cc  call    ?TraceDebugEvent@AxISEvents@@QEAAHKEPEAG@Z; AxISEvents::TraceDebugEvent(ulong,uchar,ushort *)
0x1800072d1  mov     rcx, [rsp+858h+var_28]
0x1800072d9  xor     rcx, rsp; StackCookie
0x1800072dc  call    __security_check_cookie
0x1800072e1  add     rsp, 840h
0x1800072e8  pop     rdi
0x1800072e9  pop     rsi
0x1800072ea  pop     rbx
0x1800072eb  retn
```
